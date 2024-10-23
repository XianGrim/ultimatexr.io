---
title: "UxrGrabbableObject Programming Guide"
---

# UxrGrabbableObject

## Introduction

The `UxrGrabbableObject` component, when added to a GameObject, allows the object to be manipulated by `UxrGrabber` components found in the hands of a `UxrAvatar`. The full API can be explored in the [UxrGrabbableObject API Reference](/api/T_UltimateXR_Manipulation_UxrGrabbableObject) and the user guide can be found in the [UxrGrabbableObject component guide](/docs/manipulation/uxrgrabbableobject).

Some key features include:
- **Automatic handling**: Manipulation is seamlessly managed by the `UxrGrabManager`. Once added to the scene, the grab manager handles all interactions automatically.
- **Grab, release, and place**: Objects can be grabbed, released in mid-air, or placed onto compatible `UxrGrabbableObjectAnchor` components when released close to one.
- **Multiple grab points**: Objects can be grabbed from different points, and additional grab points can be defined using `UxrGrabPointShape` components to enable more complex interactions.
- **Avatar-specific customization**: Interactions can be customized for different avatars by registering snap points and poses specifically for each avatar.
- **Hand Pose Editor support**: The Hand Pose Editor can create poses that are previewed and edited directly in the inspector window, ensuring objects are grabbed in the intended way.
- **Event support**: Events such as `Grabbed`, `Released`, and `Placed` allow custom logic to be executed when users interact with the object. Each event has both pre and post versions.
- **Constraints support**: Use events like `ConstraintsApplying`, `ConstraintsApplied`, and `ConstraintsFinished` to implement more complex behavior when objects are being manipulated.

We've divided the grabbable object programming guide into functional sections to make the information easier to navigate and access. Each section focuses on a specific area, such as hierarchy, constraints, grabbing mechanics, and more, allowing you to quickly find the details relevant to your needs.

## General Functionality

This section covers basic properties and methods that define the object's general behavior.

### Properties

- `int` `Priority`  
  Defines the object's priority for being grabbed when multiple objects are within reach.
- `bool` `AllowMultiGrab`  
  Allows the object to be grabbed by multiple grabbers at the same time.
- `bool` `IsLockedInPlace`  
  Indicates if the object is locked in place and cannot be moved.

### Methods

- `void` `ResetPositionAndState(bool propagateEvents)`  
  Resets the object’s position and state, optionally propagating events.

## Grabbable Hierararchy

This section focuses on how the grabbable object interacts with other grabbable parent or child objects in a hierarchy, controlling dependencies and manipulation across multiple objects.

A special case of a parent is a dummy parent grabbable parent.

{{% callout info %}}
A dummy parent is a parent object with an `UxrGrabbableObject` component that can only be manipulated through its children but still has its own movement and rotation constraints.
{{% /callout %}}

For example, in a door and handle setup, the door is the parent and the handle is the grabbable object. By enabling the `ControlParentDirection` property (or using the inspector), the handle can control the door’s aperture without the door being directly grabbable. You can enable the `IsDummyGrabbableParent` property (or using the inspector) to set up constraints for the parent without requiring grab points.

Other examples include an aircraft yoke, where the yoke column rotates as the child yoke object is manipulated.

### Properties

- `bool` `HasGrabbableParentDependency`  
  Indicates if this object has dependencies on a grabbable parent.
- `bool` `UsesGrabbableParentDependency`  
  Checks if the object uses its parent's dependency setup for handling grabs.
- `bool` `IgnoreGrabbableParentDependency`  
  Specifies if this object should ignore dependencies with a parent grabbable object.
- `Transform` `GrabbableParent`  
  The transform of the parent object that controls this object’s movement.
- `bool` `ControlParentDirection`  
  Determines whether the object's manipulation controls the parent’s direction through a look-at to the child.
- `bool` `IsDummyGrabbableParent`  
  Checks if the object is a dummy parent used for manipulation purposes.

## General Constraints

This section contains general rules that limit how the object can move or rotate, applying basic restrictions on its motion.

### Properties

- `bool` `IsConstrained`  
  Checks if the object has any movement constraints, such as translation or rotation limits.
- `float` `LockedGrabReleaseDistance`  
  Distance allowed before automatically releasing a grab when the object is constrained.

### Methods
  
- `void` `KeepGripsInPlace()`  
  Keeps the current grips in place after an object's `Transform` has been manually moved or rotated.
  
## Translation Constraints

This section defines how the object’s movement is limited along different axes and within certain areas, like a box or sphere.

### Properties

- `bool` `HasTranslationConstraint`  
  Indicates if the object has translation constraints applied.
- `UxrTranslationConstraintMode` `TranslationConstraint`  
  Defines the translation constraint mode for the object.
- `Vector3` `TranslationLimitsMin`  
  The minimum translation limits applied to the object in local space.
- `Vector3` `TranslationLimitsMax`  
  The maximum translation limits applied to the object in local space.
- `int` `RangeOfMotionTranslationAxisCount`  
  Gets the number of translation axes that have motion constraints.
- `IEnumerable<UxrAxis>` `RangeOfMotionTranslationAxes`  
  Returns the axes where the object can move within a defined range.
- `IEnumerable<UxrAxis>` `LimitedRangeOfMotionTranslationAxes`  
  Specifies the axes where the object’s translation is limited.
- `int` `SingleTranslationAxisIndex`  
  Gets the index of the single axis allowed for translation if applicable.
- `BoxCollider` `RestrictToBox`  
  Defines the box collider used for restricting translation when applicable.
- `SphereCollider` `RestrictToSphere`  
  Defines the sphere collider used for restricting translation when applicable.
  
## Rotation Constraints

This section covers restrictions on how the object can rotate, including the axes it can rotate around and the limits on its rotation.

### Properties

- `bool` `HasRotationConstraint`  
  Indicates if the object has rotation constraints applied.
- `UxrRotationProvider` `RotationProvider`  
  The provider that manages rotation handling when constraints are active.
- `bool` `NeedsTwoHandsToRotate`  
  Specifies if two hands are required to rotate the object.
- `UxrRotationConstraintMode` `RotationConstraint`  
  Defines the rotation constraint mode for the object.
- `Vector3` `RotationAngleLimitsMin`  
  The minimum rotation limits in local space.
- `Vector3` `RotationAngleLimitsMax`  
  The maximum rotation limits in local space.
- `int` `RangeOfMotionRotationAxisCount`  
  Gets the number of rotation axes that have motion constraints.
- `IEnumerable<UxrAxis>` `RangeOfMotionRotationAxes`  
  Returns the axes where the object can rotate within a defined range.
- `IEnumerable<UxrAxis>` `LimitedRangeOfMotionRotationAxes`  
  Specifies the axes where the object’s rotation is limited.
- `int` `SingleRotationAxisIndex`  
  Gets the index of the single axis allowed for rotation if applicable.
- `float` `SingleRotationAxisDegrees`  
  Gets or sets the rotation in degrees for objects with a single rotation axis.
- `float` `MinSingleRotationDegrees`  
  The minimum degrees allowed for objects with a single axis rotation.
- `float` `MaxSingleRotationDegrees`  
  The maximum degrees allowed for objects with a single axis rotation.
- `UxrAxis` `RotationLongitudinalAxis`  
  Defines which axis is considered the longitudinal rotation axis in rotations constrained on two or more axes.

### Methods

- `UxrAxis` `GetMostProbableLongitudinalRotationAxis()`  
  Tries to infer the most probable longitudinal rotation axis for the object.
- `UxrRotationProvider` `GetAutoRotationProvider(Vector3 gripPos)`  
  Infers the most appropriate rotation provider, the source of leverage, based on the object’s shape and grip.
  
## Resistance

This section defines how much resistance the object has to being moved or rotated, simulating physical properties like weight or friction.

### Properties

- `float` `TranslationResistance`  
  Resistance applied to translation movements.
- `float` `RotationResistance`  
  Resistance applied to rotational movements.

## Grabbing and Releasing

This section includes properties and methods related to how the object can be grabbed, held, and released by one or more hands.

### Properties

- `bool` `IsBeingGrabbed`  
  Indicates if the object is currently being grabbed.
- `bool` `IsGrabbable`  
  Gets or sets whether the object can be grabbed.
- `int` `GrabPointCount`  
  Returns the number of grab points available on the object.
- `bool` `FirstGrabPointIsMain`  
  Determines if the first grab point is the main control point in a multi-grab setup.

### Methods

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
- `void` `ReleaseGrabs(bool propagateEvents)`  
  Releases all grabbers holding the object, with an option to propagate events.

## Placement and Anchoring

This section focuses on how the object can be placed on specific anchors or snap into position when released.

### Properties

- `string` `Tag`  
  A tag that identifies which anchor components are compatible for placement.
- `Transform` `DropAlignTransform`  
  Defines the transform used for aligning the object to an anchor.
- `Transform` `DropProximityTransform`  
  Defines the transform used for checking proximity to other anchors for placement.
- `UxrGrabbableObjectAnchor` `StartAnchor`  
  The starting anchor where the object is initially placed.
- `UxrGrabbableObjectAnchor` `CurrentAnchor`  
  The anchor where the object is currently placed.
- `bool` `IsPlaceable`  
  Determines if the object can be placed on compatible anchors.
- `bool` `UseParenting`  
  Specifies if the object should be parented to the anchor or null upon grabbing or placing.
- `UxrSnapToAnchorMode` `DropSnapMode`  
  Specifies how the object snaps into place when dropped on an anchor.

### Methods

- `bool` `CanBePlacedOnAnchor(UxrGrabbableObjectAnchor anchor)`  
  Checks if the object can be placed on the specified anchor.
- `bool` `CanBePlacedOnAnchor(UxrGrabbableObjectAnchor anchor, out float distance)`  
  Checks if the object can be placed on the specified anchor and returns the euclidean distance to it.
- `void` `RemoveFromAnchor(bool propagateEvents)`  
  Removes the object from the anchor, optionally propagating events.

## Physics

This section covers physical behaviors when the object is released, like whether it becomes dynamic or how it responds to forces like throwing.

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

This section manages smooth transitions when the object is grabbed, constrained or placed, ensuring fluid and natural movements.

### Properties

- `bool` `IsInSmoothTransition`  
  Checks if the object is in a smooth transition phase.

### Methods

- `void` `StopSmoothManipulationTransition()`  
  Stops the any ongoing smooth grab transitions.
- `void` `FinishSmoothTransitions()`  
  Ends all smooth transitions, including constraints and placement.

## Events
These are events raised during object interactions, allowing custom logic to be executed when objects are grabbed, released, or placed, as well as when constraints are applied.

Refer to the [Events](/docs/programming-guide/manipulation/events#uxrgrabmanagerdocsprogramming-guidemanipulationuxrgrabmanager-events) guide for a full description.

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
