---
title: "Creating a Gun"
---

# Creating a Gun

## Weapon System Overview

In this section we'll go over a high-level overview of the components that we'll be using and what they do.

[Paste Image of Flow Chart/Diagram here?]


### Core Components

#### `UxrFirearmWeapon`
The main weapon component. It ties together:
- trigger input and shot cycle (semi/auto/manual reload)
- ammo checks (mag-based)
- recoil (procedural)
- audio + haptics
It also **requires** a `UxrProjectileSource`

#### UxrProjectileSource
The component that actually performs the shot:
- chooses a shot type (by index)
- fires using a source transform (position/forward)
- registers projectiles/shots via the weapon manager
- optionally spawns muzzle prefabs and impact prefabs  
(See Shoot(), ShotTypes, and raycast helpers.)

#### Triggers (UxrFirearmTrigger entries)
A firearm can have **one or more triggers**. Each trigger can:
- fire a different shot type (ProjectileShotIndex)
- use a different shot cycle (semi, full auto, manual reload)
- have its own recoil/audio/haptics
- optionally require a magazine anchor for ammo  
(See trigger fields: cycle type, max frequency, audio, haptics, recoil.)

#### Mag Anchor + Mag (UxrGrabbableObjectAnchor + UxrFirearmMag)
- The **mag anchor** is where a magazine physically attaches.
- The **mag** stores ammo:
  - Capacity = max rounds
  - Rounds = remaining rounds (clamped) and raises a change event  
(See Capacity/Rounds and RoundsChanged.)

#### Recoil
Recoil is applied after constraints so it happens in the correct order. Recoil is configurable per trigger:
- one-hand recoil angle/offset
- two-hand recoil angle/offset
- recoil duration  
(Recoil is applied using recoil axes or the weapon transform.)

### Optional Components

#### UxrFirearmAmmoLabel
A simple UI helper that draws ammo remaining (and optionally capacity) from a chosen trigger index.

---

## Setting Up the Model

Recommended hierarchy:

- **Gun** (Empty GameObject) ← *all weapon components live here*
  - **Gun_Model** (Empty GameObject) ← *middleman for easy swapping/scaling*
    - **GunMesh** (your mesh/model)
  - **ShotSource** (Empty GameObject) ← *muzzle / bullet origin*
  - **Tip** (Optional) ← *muzzle flash spawn transform if used*
  - **TriggerTransform** (Optional) ← *a child transform that visually rotates*
  - **MagAnchor** (Empty GameObject) ← *where the magazine will seat*

> The “middleman” model object keeps your weapon logic unscaled and makes swapping meshes painless.

---

## Add Components and References (Minimum Working Setup)

### 1) Add UxrGrabbableObject (Grip)
- Add a `UxrGrabbableObject` to **Gun**
- Create your main grip pose(s)
- Confirm you can pick up the gun in play mode

### 2) Add UxrProjectileSource
- Add `UxrProjectileSource` to **Gun**
- Add at least **one shot type** entry
- Assign:
  - ShotSource transform (muzzle)
  - projectile prefab / max distance / collision layers as needed
  - optional muzzle prefab / impact prefab

### 3) Add UxrFirearmWeapon
- Add `UxrFirearmWeapon` to **Gun**
- Assign:
  - RecoilAxes transform (optional but recommended)
- Add **Triggers** entries:
  - ProjectileShotIndex (maps to ProjectileSource shot type index)
  - CycleType (SemiAutomatic is a good first test)
  - MaxShotFrequency
  - TriggerGrabbable + GrabPointIndex
  - TriggerTransform (optional, for visuals)
  - Recoil settings (start subtle)
  - Shot audio + no-ammo audio + haptics (optional)

> If you add multiple triggers (example: rifle + grenade launcher), your `UxrProjectileSource` should have the same number of shot types as triggers.

---

## Magazine Setup (Optional, but recommended)

### Create the Magazine
- Make a mag prefab with `UxrGrabbableObject`
- Add `UxrFirearmMag`
- Set:
  - Capacity
  - starting Rounds

### Add a Mag Anchor to the Gun
- Add a `UxrGrabbableObjectAnchor` at **MagAnchor**
- Assign it in the trigger’s AmmunitionMagAnchor field

> No mag anchor = effectively infinite ammo (the firearm returns int.MaxValue for ammo).

---

## Test Fire

### If it doesn't shoot, check these first
- Does the gun have both `UxrFirearmWeapon` and `UxrProjectileSource`? (Required)
- Does `ProjectileShotIndex` match a valid ShotTypes index?
- Is ShotSource forward (Z+) pointing out of the barrel?
- Are you out of ammo? (Ammo left must be > 0 to shoot)
- Is MaxShotFrequency preventing another shot?

---

## Extras (Polish)

### Debug Helpers
- Draw a gizmo line from ShotSource forward
- Log ammo remaining on shot
- Temporary UI text showing trigger press amount

### Muzzle Flash
- Use the projectile source shot type option to instantiate a prefab at the tip when shot (optional lifetime, optional parent).

### Mag Seat Audio
- Play a “click” sound when the anchor Placed event fires
- Optional: play a “remove” sound on Removed

---

## Damage Events

### Dealing Damage
- Decide whether your shots are:
  - physical projectile collisions, or
  - raycast hits
- On hit, send a damage payload to the hit target (interface recommended)

### Taking Damage
- Add a health/damage receiver component to targets
- Apply damage, play hit VFX/SFX, and handle death/disable logic
