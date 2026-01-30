---
title: "Creating a Gun"
---

# Creating a Gun
![](/media/docs/tutorials/weapons/creating-a-gun/pistol-on-table.png)

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
- **requires** a `UxrProjectileSource`

#### `UxrProjectileSource`
The component that actually performs the shot:
- chooses a shot type (by index)
- fires using a source transform (position/forward)
- registers projectiles/shots via the weapon manager
- optionally spawns muzzle prefabs and impact prefabs  

#### Triggers (`UxrFirearmTrigger` entries)
A firearm can have **one or more triggers**. Each trigger can:
- fire a different shot type (ProjectileShotIndex)
- use a different shot cycle (semi, full auto, manual reload)
- have its own recoil/audio/haptics
- optionally require a magazine anchor for ammo  

#### Mag Anchor + Mag (`UxrGrabbableObjectAnchor` + `UxrFirearmMag`)
- The **mag anchor** is where a magazine physically attaches.
- The **mag** stores ammo:
  - Capacity = max rounds
  - Rounds = remaining rounds (clamped) and raises a change event  

#### Recoil
Recoil is applied after constraints so it happens in the correct order. Recoil is configurable per trigger:
- one-hand recoil angle/offset
- two-hand recoil angle/offset
- recoil duration  
(Recoil is applied using recoil axes or the weapon transform.)

### Optional Components

#### `UxrFirearmAmmoLabel`
A simple UI helper that draws ammo remaining (and optionally capacity) from a chosen trigger index.

---

## Setting Up the Model
Let's get a basic weapon working! This will cover to minimum requirements to create a functional weapon. We'll cover more areas in the Polish section.

First, add your desired weapon model to the scene. Next, we'll set up the recommended hierarchy for the weapon:
- **Gun** (Empty GameObject) ← *logic (components) will live here*
  - **Gun Model** (Empty GameObject) ← *middleman for easy swapping/scaling but optional*
    - **GunMesh** (your mesh/model)

![](/media/docs/tutorials/weapons/creating-a-gun/gun-3-tier-setup.png)
> The “middleman” model object is recommended due to how it keeps your weapon logic unscaled and makes swapping meshes/models painless.

After adding your model, you may need to reset the position and rotation
![](/media/docs/tutorials/weapons/creating-a-gun/pistol-model-scale.png)
{{% callout tip %}}
- Feel free to leave the scale of the model at the same values it was imported in as. Use the middleman ("Gun Model") object if you need to adjust the scale.
- If your model seems to disappear after reseting the rotation and position, the root Gun object is most likely out of view. Select it in the heirarchy, then press the "F" key to auto-focus on it.
{{% /callout %}}


  - **ShotSource** (Empty GameObject) ← *muzzle / bullet origin*
  - **Tip** (Optional) ← *muzzle flash spawn transform if used*
  - **TriggerTransform** (Optional) ← *a child transform that visually rotates*
  - **MagAnchor** (Empty GameObject) ← *where the magazine will seat*

Next, we'll add a few more empty game objects which we'll use later as reference points.
- ShotSource
- Tip
- Recoil (if recoil isn't wanted, you can skip this one!)
![](/media/docs/tutorials/weapons/creating-a-gun/gun-reference-points.png)

And with those reference points added, we can start adding components!

## Components and References
First, lets start by adding the `UxrGrabbableObject` component so that we can pick up our weapon. Remember to add the component to our base "Gun" object and not the middleman or model. After adding the component, set up the grabs as normal 
{{% callout tip %}}
Check out our other guides, such as grabbing a ball or creating a staff if you need more information on this component!
{{% /callout %}}

As you can see from the image below, the model we are using looks a bit too big. We can use our middleman object to adjust it's scale down to a value that fits better. This value may be different for your model, just set it to a value you like!
![](/media/docs/tutorials/weapons/creating-a-gun/pistol-too-big.png)

For the pose, we'll select either a generic one or DemoGun for now. Even if the pose may not fit your model completely, we want to get the gun working at the moment. We can come back at the end and add details/polish!

Once a quick pose is added, let's hop into play mode and test our grabbable!
{{< video src="/media/docs/tutorials/weapons/creating-a-gun/Gun-first-grabbable.mp4" >}}
{{% callout tip %}}
Doing these small "sanity" checks can help you catch any issues or bugs early!
{{% /callout %}}

### Add the UxrFirearmWeapon Component

Select the Gun object, the main root object, where the `UXRGrabbableObject` is, and add the `UxrFirearmWeapon`. The `UxrProjectileSource` will be added automatically, as it is required.
![](/media/docs/tutorials/weapons/creating-a-gun/pistol-firearm-component.png)

Next, we'll set up the firearm component. Open the Trigger drop-down menu in the `UxrFirearmWeapon`, then select the + icon to add a trigger.
![](/media/docs/tutorials/weapons/creating-a-gun/pistol-component-trigger.png)
![](/media/docs/tutorials/weapons/creating-a-gun/pistol-trigger-component.png)
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
