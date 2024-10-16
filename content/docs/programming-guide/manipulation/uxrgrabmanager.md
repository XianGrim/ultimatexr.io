---
title: "UxrGrabManager"
---

# UxrGrabManager

## Introduction
`UxrGrabManager` is the central class managing manipulation interactions in UltimateXR. It is responsible for updating all manipulation-related components each frame.

This guide will show you how to program using the `UxrGrabManager`. While the manager provides standard grab mechanics automatically, allowing avatars to interact with the environment through manipulation components, programming can be used for additional tasks such as:
- Writing code that reacts to manipulation events.
- Querying information about current grabs.
- Executing actions like grabbing, releasing, or placing objects programmatically.

These are just a few examples. Below, we will list all the functionality that `UxrGrabManager` provides.

## Singleton
`UxrGrabManager` is a [singleton](/docs/programming-guide/architecture/singletons) that is created automatically during startup. The global instance can be accessed from anywhere in the code through `UxrGrabManager.Instance:full`.

## Core Responsibilities
At runtime, `UxrGrabManager` monitors input events and reacts to user actions like grabbing or releasing objects. These interactions are handled automatically with the help of other components such as:
- [UxrGrabber](/docs/programming-guide/manipulation/uxrgrabber): Component on avatar hands that enable grabbing.
- [UxrGrabbableObject](/docs/programming-guide/manipulation/uxrgrabbableobject): Component added to objects enabling grabbing and describing how.
- [UxrGrabbableObjectAnchor](/docs/programming-guide/manipulation/uxrgrabbableobjectanchor): Component on points in space where objects can be snapped to.

The manager’s responsibilities include:
- **Tracking manipulation components**: Monitoring all grabbers, grabbable objects, and anchors in the scene.
- **Handling interactions**: Managing actions like grabbing, placing objects on anchors, releasing, and throwing.
- **Applying constraints**: Enforcing limits on object movement and rotation.
- **Ensuring smooth transitions**: Performing manipulation actions with smooth, glitch-free movements.
- **Updating affordances**: Maintaining visual cues that show how objects can be interacted with.
- **Raising events**: Notifying users of key actions to enable custom reactions.
- **Syncing manipulation**: Ensuring consistency in multiplayer sessions.

## Enabling/Disabling Features

## Event System
`UxrGrabManager` provides several key events to track object interactions:
- **GrabTrying**
- **ObjectGrabbing/ObjectGrabbed**
- **ObjectReleasing/ObjectReleased**
- **ObjectPlacing/ObjectPlaced**

## Properties

## Methods

## API Reference

For more information, refer to the [UxrGrabManager API Reference](/api/T_UltimateXR_Manipulation_UxrGrabManager).
