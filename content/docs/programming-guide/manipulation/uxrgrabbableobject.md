---
title: "UxrGrabbableObject Programming Guide"
---

# UxrGrabbableObject

## Introduction

The `UxrGrabbableObject` component, when added to a GameObject, allows the object to be manipulated by `UxrGrabber` components found in the hands of a `UxrAvatar`. 

Some key features include:
- **Automatic handling**: Manipulation is seamlessly managed by the `UxrGrabManager`. Once added to the scene, the grab manager handles all interactions automatically.
- **Grab, release, and place**: Objects can be grabbed, released in mid-air, or placed onto compatible `UxrGrabbableObjectAnchor` components when released close to one.
- **Multiple grab points**: Objects can be grabbed from different points, and additional grab points can be defined using `UxrGrabPointShape` components to enable more complex interactions.
- **Avatar-specific customization**: Interactions can be customized for different avatars by registering snap points and poses specifically for each avatar.
- **Hand Pose Editor support**: The Hand Pose Editor can create poses that are previewed and edited directly in the inspector window, ensuring objects are grabbed in the intended way.
- **Event support**: Events such as `Grabbed`, `Released`, and `Placed` allow custom logic to be executed when users interact with the object. Each event has both pre and post versions.
- **Constraints support**: Use events like `ConstraintsApplying`, `ConstraintsApplied`, and `ConstraintsFinished` to implement more complex behavior when objects are being manipulated.

## General Properties

### Properties

- `bool` `IsLockedInPlace`  
  Indicates if the object is locked in place and cannot be moved.
- `bool` `AllowMultiGrab`  
  Allows the object to be grabbed by multiple grabbers at the same time.
- `int` `Priority`  
  Defines the object's priority for being grabbed when multiple objects are within reach.

### Methods

- `void` `ResetPositionAndState(bool propagateEvents)`  
  Resets the object’s position and state, optionally propagating events.

## Grab Hieararchy

### Properties

- `bool` `IsDummyGrabbableParent`  
  Checks if the object is a dummy parent used for manipulation purposes.
- `bool` `ControlParentDirection`  
  Determines whether the parent’s direction is controlled during grabbing.
- `bool` `IgnoreGrabbableParentDependency`  
  Specifies if this object should ignore dependencies with a parent grabbable object.
- `bool` `HasGrabbableParentDependency`  
  Indicates if this object has dependencies on a grabbable parent.
- `bool` `UsesGrabbableParentDependency`  
  Checks if the object uses its parent's dependency setup for handling grabs.
- `Transform` `GrabbableParent`  
  The transform of the parent object that controls this object’s movement.

## Constraints and Resistance

### Properties

- `bool` `IsConstrained`  
  Checks if the object has any movement constraints, such as translation or rotation limits.
- `bool` `HasTranslationConstraint`  
  Indicates if the object has translation constraints applied.
- `bool` `HasRotationConstraint`  
  Indicates if the object has rotation constraints applied.
- `UxrRotationProvider` `RotationProvider`  
  The provider that manages rotation handling when constraints are active.
- `bool` `NeedsTwoHandsToRotate`  
  Specifies if two hands are required to rotate the object.
- `int` `RangeOfMotionTranslationAxisCount`  
  Gets the number of translation axes that have motion constraints.
- `int` `RangeOfMotionRotationAxisCount`  
  Gets the number of rotation axes that have motion constraints.
- `Vector3` `RangeOfMotionTranslationAxes`  
  Returns the axes where the object can move within a defined range.
- `Vector3` `RangeOfMotionRotationAxes`  
  Returns the axes where the object can rotate within a defined range.
- `Vector3` `LimitedRangeOfMotionTranslationAxes`  
  Specifies the axes where the object’s translation is limited.
- `Vector3` `LimitedRangeOfMotionRotationAxes`  
  Specifies the axes where the object’s rotation is limited.
- `int` `SingleTranslationAxisIndex`  
  Gets the index of the single axis allowed for translation if applicable.
- `int` `SingleRotationAxisIndex`  
  Gets the index of the single axis allowed for rotation if applicable.
- `float` `SingleRotationAxisDegrees`  
  Gets or sets the rotation in degrees for objects with a single rotation axis.
- `float` `LockedGrabReleaseDistance`  
  Distance allowed for releasing the grab when the object is locked.
- `float` `MinSingleRotationDegrees`  
  The minimum degrees allowed for objects with a single axis rotation.
- `float` `MaxSingleRotationDegrees`  
  The maximum degrees allowed for objects with a single axis rotation.
- `UxrTranslationConstraintMode` `TranslationConstraint`  
  Defines the translation constraint mode for the object.
- `BoxCollider` `RestrictToBox`  
  Defines the box collider used for restricting translation when applicable.
- `SphereCollider` `RestrictToSphere`  
  Defines the sphere collider used for restricting translation when applicable.
- `Vector3` `TranslationLimitsMin`  
  The minimum translation limits applied to the object in local space.
- `Vector3` `TranslationLimitsMax`  
  The maximum translation limits applied to the object in local space.
- `UxrRotationConstraintMode` `RotationConstraint`  
  Defines the rotation constraint mode for the object.
- `UxrAxis` `RotationLongitudinalAxis`  
  Defines which axis is considered the longitudinal rotation axis in constrained rotations.
- `Vector3` `RotationAngleLimitsMin`  
  The minimum rotation limits in local space.
- `Vector3` `RotationAngleLimitsMax`  
  The maximum rotation limits in local space.
- `float` `TranslationResistance`  
  Resistance applied to translation movements.
- `float` `RotationResistance`  
  Resistance applied to rotational movements.

### Methods

- `void` `KeepGripsInPlace()`  
  Keeps the current grips in place without releasing them.
- `UxrAxis` `GetMostProbableLongitudinalRotationAxis()`  
  Returns the most probable longitudinal rotation axis for the object.
- `UxrRotationProvider` `GetAutoRotationProvider(Vector3 gripPos)`  
  Infers the most appropriate rotation provider based on the object’s shape and grip.

## Grabbing and Releasing

### Properties

- `bool` `IsBeingGrabbed`  
  Indicates if the object is currently being grabbed.
- `bool` `IsGrabbable`  
  Specifies if the object is grabbable at the current time.
- `int` `GrabPointCount`  
  Returns the number of grab points available on the object.
- `bool` `FirstGrabPointIsMain`  
  Determines if the first grab point is the main control point in a multi-grab setup.

### Methods

- `void` `ReleaseGrabs(bool propagateEvents)`  
  Releases all grabbers holding the object, with an option to propagate events.
- `UxrGrabPointInfo` `GetGrabPoint(int index)`  
  Returns information about the grab point at the specified index.
- `void` `SetGrabPointEnabled(int index, bool enabled)`  
  Enables or disables the grab point at the specified index.
- `void` `EnableAllGrabPoints(bool enabled)`  
  Enables or disables all grab points on the object.
- `float` `GetDistanceFromGrabber(UxrGrabber grabber, int grabPoint)`  
  Returns the distance between the grabber and the specified grab point.
- `bool` `CanBeGrabbedByGrabber(UxrGrabber grabber, int grabPoint)`  
  Checks if the object can be grabbed by the specified grabber using the given grab point.
- `bool` `ComputeRequiredGrabberTransform(UxrGrabber grabber, int grabPoint, out Vector3 grabberPosition, out Quaternion grabberRotation)`  
  Computes the required position and rotation for the grabber to hold the object.

## Placement and Anchoring

### Properties

- `string` `Tag`  
  A tag that identifies which anchor components are compatible for placement.
- `Transform` `DropAlignTransform`  
  Defines the transform used for aligning the object during drop.
- `Transform` `DropProximityTransform`  
  Defines the transform used for checking proximity when dropping the object.
- `UxrGrabbableObjectAnchor` `StartAnchor`  
  The starting anchor where the object is initially placed.
- `UxrGrabbableObjectAnchor` `CurrentAnchor`  
  The anchor where the object is currently placed.
- `bool` `IsPlaceable`  
  Determines if the object can be placed on a compatible anchor.
- `bool` `UseParenting`  
  Specifies if the object should be parented to the anchor or null upon grabbing or placing.
- `UxrSnapToAnchorMode` `DropSnapMode`  
  Specifies how the object snaps into place when dropped on an anchor.

### Methods

- `bool` `CanBePlacedOnAnchor(UxrGrabbableObjectAnchor anchor)`  
  Checks if the object can be placed on the specified anchor.
- `bool` `UxrGrabbableObject.CanBePlacedOnAnchor(UxrGrabbableObjectAnchor anchor, out float distance)`  
  Checks if the object can be placed on the specified anchor and returns the euclidean distance to it.
- `void` `RemoveFromAnchor(bool propagateEvents)`  
  Removes the object from the anchor, optionally propagating events.

## Physics

### Properties

- `Rigidbody` `RigidBodySource`  
  The rigid body that controls physics-based movements.
- `bool` `RigidBodyDynamicOnRelease`  
  Indicates if the rigid body should switch to dynamic mode when released.
- `bool` `CanUseRigidBody`  
  Checks if the object can utilize a rigid body for physics-based manipulation.
- `float` `VerticalReleaseMultiplier`  
  Multiplier applied to vertical movement when the object is released.
- `float` `HorizontalReleaseMultiplier`  
  Multiplier applied to horizontal movement when the object is released.
- `bool` `IsKinematic`  
  Indicates if the object is kinematic, affecting how physics interactions are handled.

## Transitions

### Properties

- `bool` `IsInSmoothTransition`  
  Checks if the object is in a smooth transition phase.

### Methods

- `void` `StopSmoothManipulationTransition()`  
  Stops any ongoing smooth manipulation transitions.
- `void` `FinishSmoothTransitions()`  
  Ends all smooth transitions, allowing direct manipulation of the object.

## Events
These are events raised during object interactions, allowing custom logic to be executed when objects are grabbed, released, or placed, as well as when constraints are applied.

- `ConstraintsApplying`  
  Raised when constraints are about to be applied to the object.
- `ConstraintsApplied`  
  Raised after constraints have been applied to the object.
- `ConstraintsFinished`  
  Raised after all constraint handlers have been executed.
- `Grabbing`  
  Raised when the object is being grabbed.
- `Grabbed`  
  Raised after the object has been successfully grabbed.
- `Releasing`  
  Raised when the object is being released.
- `Released`  
  Raised after the object has been released.
- `Placing`  
  Raised when the object is being placed on an anchor.
- `Placed`  
  Raised after the object has been placed on an anchor.
