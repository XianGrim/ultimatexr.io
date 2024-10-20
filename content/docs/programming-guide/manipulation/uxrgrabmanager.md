---
title: "UxrGrabManager Programming Guide"
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

## Events
`UxrGrabManager` provides several key events to track object interactions. Refer to the [Events](/docs/programming-guide/manipulation/events#uxrgrabmanagerdocsprogramming-guidemanipulationuxrgrabmanager-events) guide for more information

## Properties

### Features

The `UxrGrabManager.Features` property, which uses the `UxrManipulationFeatures` flags, allows control over which manipulation features are enabled during object interaction. By configuring this property, you can toggle specific features such as object constraints, smooth transitions, affordances, and more.

- **ObjectManipulation**: Updates the transform of `UxrGrabbableObject` based on user interaction.
- **ObjectConstraints**: Applies constraints set in the `UxrGrabbableObject` component.
- **ObjectResistance**: Adds resistance for translation and rotation.
- **UserConstraints**: Handles custom constraints defined by the user.
- **KeepGripsInPlace**: Prevents hand drift when constraints are applied.
- **SmoothTransitions**: Ensures smooth transitions during manipulation.
- **Affordances**: Updates object interaction cues.
- **All**: Enables all features.

By default, all features are enabled.

## Query Methods

The querying methods in `UxrGrabManager` allow you to gather detailed information about the current state of grabbable objects, grabbers, and interactions in your scene.
These methods help determine which objects are being grabbed, the grab points in use, velocities, and whether certain hand actions are possible.

For a full description of these methods, refer to the [UxrGrabManager API Reference](/api/T_UltimateXR_Manipulation_UxrGrabManager#methods).

### Possibility To Grab

- `CanGrabSomething(UxrAvatar avatar, UxrHandSide handSide)`  
  Checks if the given avatar can grab something with the specified hand.

- `UxrGrabManager.CanGrabSomething(UxrGrabber grabber)`  
  Checks if the specified grabber can grab an object.
  
### Closest Grabbable Object

- `UxrGrabManager.GetClosestGrabbableObject(UxrAvatar avatar, UxrHandSide handSide, out UxrGrabbableObject grabbableObject)`  
  Finds the closest grabbable object that can be grabbed by the given avatar and hand.

- `UxrGrabManager.GetClosestGrabbableObject(UxrAvatar avatar, UxrHandSide handSide, out UxrGrabbableObject grabbableObject, out int grabPoint, IEnumerable<UxrGrabbableObject> candidates = null)`  
  Finds the closest grabbable object and grab point that can be grabbed by the avatar's hand.

- `UxrGrabManager.GetClosestGrabbableObject(UxrGrabber grabber, out UxrGrabbableObject grabbableObject, out int grabPoint, IEnumerable<UxrGrabbableObject> candidates = null)`  
  Finds the closest grabbable object and grab point for a specific grabber.
  
### Hand Rendering

- `UxrGrabManager.ShouldHideHandRenderer(UxrGrabber grabber, UxrGrabbableObject grabbableObject)`  
  Checks whether the hand renderer should be hidden when grabbing the specified object.
  
### Grab Pose

- `UxrGrabManager.GetOverrideGrabPoseName(UxrGrabber grabber, UxrGrabbableObject grabbableObject)`  
  Returns the grab pose name for the object, or null if the default pose should be used.

- `UxrGrabManager.GetOverrideGrabPoseBlendValue(UxrGrabber grabber, UxrGrabbableObject grabbableObject)`  
  Gets the blend value used for the grab pose state during the grab. The pose should be a `UxrHandPoseType.Blend` pose type.
  
### Grab Information

- `UxrGrabManager.IsHandGrabbing(UxrAvatar avatar, UxrHandSide handSide)`  
  Checks if the specified avatar's hand is currently grabbing something.

- `UxrGrabManager.IsHandGrabbing(UxrAvatar avatar, UxrGrabbableObject grabbableObject, UxrHandSide handSide, bool alsoCheckDependentGrab)`  
  Checks if the avatar's hand is grabbing the specified object or any connected objects.

- `UxrGrabManager.GetObjectsBeingGrabbed()`  
  Returns an iterator for all currently grabbed objects.

- `UxrGrabManager.GetObjectBeingGrabbed(UxrAvatar avatar, UxrHandSide handSide, out UxrGrabbableObject grabbableObject)`  
  Gets the object being grabbed by the specified avatar's hand.

- `UxrGrabManager.GetHandsGrabbingCount(UxrGrabbableObject grabbableObject, bool alsoCheckDependentGrabs = true)`  
  Returns the number of hands grabbing the object.

- `UxrGrabManager.IsBeingGrabbed(UxrGrabbableObject grabbableObject)`  
  Checks if the object is currently being grabbed.

- `UxrGrabManager.IsBeingGrabbed(UxrGrabbableObject grabbableObject, int point)`  
  Checks if a specific grab point on the object is being grabbed.

- `UxrGrabManager.IsBeingGrabbedBy(UxrGrabbableObject grabbableObject, UxrAvatar avatar)`  
  Checks if the object is being grabbed by the specified avatar.

- `UxrGrabManager.IsBeingGrabbedBy(UxrGrabbableObject grabbableObject, UxrGrabber grabber)`  
  Checks if the object is being grabbed by the specified grabber.

- `UxrGrabManager.IsBeingGrabbedByOtherThan(UxrGrabbableObject grabbableObject, int point)`  
  Checks if the object is being grabbed using any grab point other than the specified one.

- `UxrGrabManager.IsBeingGrabbedByOtherThan(UxrGrabbableObject grabbableObject, int point, UxrGrabber grabber)`  
  Checks if the object is being grabbed by any other grabber or point than the specified ones.

- `UxrGrabManager.GetGrabbingHand(UxrGrabbableObject grabbableObject, out bool isLeft, out bool isRight)`  
  Determines whether the object is being grabbed by the left or right hand.

- `UxrGrabManager.GetGrabbingHand(UxrGrabbableObject grabbableObject, int point, out UxrGrabber grabber)`  
  Gets the grabber holding the object at a specific grab point.

- `UxrGrabManager.GetGrabbingHand(UxrGrabbableObject grabbableObject, int point, out UxrHandSide handSide)`  
  Gets the hand side grabbing the object at a specific grab point.

- `UxrGrabManager.GetGrabbingHands(UxrGrabbableObject grabbableObject, int point, out List<UxrGrabber> grabbers)`  
  Retrieves all grabbers holding the object at a specific grab point.

- `UxrGrabManager.GetGrabbingHands(UxrGrabbableObject grabbableObject, int point = -1)`  
  Returns all grabbers holding the object at any grab point.

- `UxrGrabManager.GetGrabbedPoint(UxrGrabber grabber)`  
  Returns the index of the grab point currently being grabbed by the specified grabber.

- `UxrGrabManager.GetGrabbedPointCount(UxrGrabbableObject grabbableObject)`  
  Returns the number of grab points currently being held on the object.

- `UxrGrabManager.GetGrabbingHandCount(UxrGrabbableObject grabbableObject, bool includeChildGrabs = true)`  
  Returns the total number of hands grabbing the object.

- `UxrGrabManager.GetGrabbedObjectAnchorFrom(UxrGrabbableObject grabbableObject)`  
  Returns the anchor from which the object was grabbed.
  
### Velocities

- `UxrGrabManager.GetGrabbedObjectVelocity(UxrGrabbableObject grabbableObject, bool smooth = true)`  
  Retrieves the current velocity of the object being grabbed.

- `UxrGrabManager.GetGrabbedObjectAngularVelocity(UxrGrabbableObject grabbableObject, bool smooth = true)`  
  Retrieves the current angular velocity of the object being grabbed.

## Manipulation Methods

The manipulation methods in `UxrGrabManager` provide direct control over object interactions, enabling you to programmatically execute grabs, releases, and placements.
It also allows to control object movement and rotation, while applying constraints.

### Executing Manipulation Actions

- `UxrGrabManager.TryGrab(UxrAvatar avatar, UxrHandSide handSide)`  
  Attempts to grab an object using the avatar’s specified hand. Returns the `UxrGrabber` that successfully grabbed an object, if any.

- `UxrGrabManager.TryRelease(UxrAvatar avatar, UxrHandSide handSide)`  
  Attempts to release an object being held by the avatar’s specified hand. Returns the `UxrGrabber` that released the object, if any.

- `UxrGrabManager.GrabObject(UxrGrabber grabber, UxrGrabbableObject grabbableObject, int grabPoint, bool propagateEvents)`  
  Forces a specific grabber to grab the specified object at a particular grab point. Optionally propagates events.

- `UxrGrabManager.ReleaseObject(UxrGrabber grabber, UxrGrabbableObject grabbableObject, bool propagateEvents)`  
  Releases a specified object from a grabber or all grabbers if the grabber is null. Optionally propagates events.

- `UxrGrabManager.ReleaseGrabs(UxrGrabbableObject grabbableObject, bool propagateEvents)`  
  Releases all active grabs on the specified object. Optionally propagates events.

- `UxrGrabManager.PlaceObject(UxrGrabbableObject grabbableObject, UxrGrabbableObjectAnchor anchor, UxrPlacementOptions placementOptions, bool propagateEvents)`  
  Places the specified object on an anchor with the given placement options. It can also release grips based on the placement options and optionally propagate events.

- `UxrGrabManager.RemoveObjectFromAnchor(UxrGrabbableObject grabbableObject, bool propagateEvents)`  
  Removes the specified object from its current anchor and optionally propagates events.
  
### Moving/Rotating Applying Constraints

- `UxrGrabManager.SetPositionUsingConstraints(UxrGrabbableObject grabbableObject, Vector3 position, bool useResistance, bool propagateEvents)`  
  Moves the object to a new world position, applying constraints and resistance as necessary. Optionally propagates events.

- `UxrGrabManager.SetRotationUsingConstraints(UxrGrabbableObject grabbableObject, Quaternion rotation, bool useResistance, bool propagateEvents)`  
  Rotates the object to a new world rotation, applying constraints and resistance as necessary. Optionally propagates events.

- `UxrGrabManager.SetPositionAndRotationUsingConstraints(UxrGrabbableObject grabbableObject, Vector3 position, Quaternion rotation, bool useResistance, bool propagateEvents)`  
  Moves and rotates the object to a new world position and rotation, applying constraints and resistance. Optionally propagates events.

- `UxrGrabManager.SetLocalPositionUsingConstraints(UxrGrabbableObject grabbableObject, Vector3 localPosition, bool useResistance, bool propagateEvents)`  
  Moves the object to a new local position, applying constraints and resistance as necessary. Optionally propagates events.

- `UxrGrabManager.SetLocalRotationUsingConstraints(UxrGrabbableObject grabbableObject, Quaternion localRotation, bool useResistance, bool propagateEvents)`  
  Rotates the object to a new local rotation, applying constraints and resistance as necessary. Optionally propagates events.

- `UxrGrabManager.SetLocalPositionAndRotationUsingConstraints(UxrGrabbableObject grabbableObject, Vector3 localPosition, Quaternion localRotation, bool useResistance, bool propagateEvents)`  
  Moves and rotates the object to a new local position and rotation, applying constraints and resistance as necessary. Optionally propagates events.
  
### Keeping Grips In Place

The avatar hands are not automatically repositioned when a grabbed object's `Transform` is manually altered. These methods will update the hands to ensure that they maintain their original grip position after the object has been moved manually.

- `UxrGrabManager.KeepGripsInPlace(UxrGrabbableObject grabbableObject)`  
  Ensures that all grips holding the object stay in place after it has been manipulated or constrained.

- `UxrGrabManager.KeepGripInPlace(UxrGrabber grabber)`  
  Ensures that a specific grip remains in the correct position after manipulating or constraining the object.
  
### Objects Constrained To a Single Rotation Axis

These are objects that can rotate along a single axis only, such as a steering wheel, door handle, or knob.

- `UxrGrabManager.GetObjectSingleRotationAxisDegrees(UxrGrabbableObject grabbableObject)`  
  Retrieves the current rotation angle (in degrees) for objects constrained to a single axis of rotation.

- `UxrGrabManager.SetObjectSingleRotationAxisDegrees(UxrGrabbableObject grabbableObject, float degrees)`  
  Sets the rotation angle (in degrees) for objects with a single axis of rotation, taking rotation limits into account.

## API Reference

For more information, refer to the [UxrGrabManager API Reference](/api/T_UltimateXR_Manipulation_UxrGrabManager).
