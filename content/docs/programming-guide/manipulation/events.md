---
title: "Manipulation Events"
---

# Events

UltimateXR provides an event-based system for its manipulation module that allows developers to respond to specific actions and interactions. These events can be tied to grabbing, releasing, or interacting with objects, giving you full control over how your application reacts to them.

You can access these events in two ways: 

1. **Using `UxrGrabManager`**: This lets you track all object interactions.
2. **Directly from a `UxrGrabbableObject` or `UxrGrabbableObjectAnchor`**: Use this when you only need to track events for a specific object.

We’ll also cover `UxrGrabbableObjectComponent`, which allows you to handle events by overriding specific methods through inheritance.

## Manipulation Events in UltimateXR

Events in UltimateXR use standard C# event mechanics. You subscribe to events when needed and unsubscribe when they are no longer necessary. Here’s an example of how to detect when an object is grabbed:

```c#
class MyGrabLogger : MonoBehaviour
{
	// Subscribe to event
	private void OnEnable()
	{
		UxrGrabManager.Instance.ObjectGrabbed += UxrGrabManager_ObjectGrabbed;
	}

	// Unsubscribe from event
	private void OnDisable()
	{
		UxrGrabManager.Instance.ObjectGrabbed -= UxrGrabManager_ObjectGrabbed;
	}
	
	// This is the event handling method and receives manipulation event arguments
	private void UxrGrabManager_ObjectGrabbed(object sender, UxrManipulationEventArgs e)
	{
		Debug.Log($"Object {e.GrabbableObject.name} was grabbed");
	}
}
```

In the example above, the `MyGrabLogger` component subscribes to the *Grabbed* event when first activated, and unsubscribes from it when being destroyed. The component will print a message on the log window every time a component is grabbed.

We recommend two approaches for handling events:

1. **Subscribe during `OnEnable()`, unsubscribe during `OnDisable()`**: Use this when you want event notifications only while the component is enabled. 
2. **Subscribe during `Awake()` or `Start()`, unsubscribe during `OnDestroy()`**: Use this when you need event notifications even while the component is disabled or inactive.

The first approach is usually recommended because, in most cases, a disabled component should not process or handle any data.

{{% callout caution %}}
Not unsubscribing from events can lead to null reference exceptions. This happens because the event handling method will still be called on an object that has been deleted.
{{% /callout %}}

## `UxrGrabManager` Events
These events are raised whenever any element in the scene activates them. They all receive a `UxrManipulationEventArgs` object that contains specific manipulation information about the event. Depending on which event is being raised, some fields may be left unused. For example, a *Grabbed* will never use the `UxrManipulationEventArgs.ReleaseVelocity` property.

The `UxrManipulationEventArgs` class has the following properties:

- **IsGrabbedStateChanged**: Indicates whether the object switched between being grabbed and not being grabbed, filtering out cases where it's still grabbed by another hand.
- **EventType**: The type of event (e.g., grabbing, releasing).
- **GrabbableObject**: The object involved in the manipulation.
- **GrabbableAnchor**: The anchor related to the event.
- **Grabber**: The entity performing the action.
- **GrabPointIndex**: The grab point index for the object.
- **IsMultiHands**: Indicates if more than one hand is involved.
- **IsSwitchHands**: Indicates if the object was passed between hands.
- **ReleaseVelocity**: The release velocity.
- **ReleaseAngularVelocity**: The angular velocity on release.
- **PlacementOptions**: The placement flags in place events.

Check the [UxrGrabManager Event API Reference](/api/T_UltimateXR_Manipulation_UxrGrabManager#events) to see how these properties are used.

### GrabTrying
Triggered when the user presses the grab action button on the controller, indicating an attempt to grab. This doesn’t necessarily mean an object is within reach; it just shows that the user has pressed the button.

### ObjectGrabbing/ObjectGrabbed
Triggered right before an object is being grabbed (`UxrGrabManager.ObjectGrabbing`) and when the grab is complete (`UxrGrabManager.ObjectGrabbed`).

### ObjectReleasing/ObjectReleased
Triggered when an object starts to be released (`UxrGrabManager.ObjectReleasing`) and when the release is complete (`UxrGrabManager.ObjectReleased`).

### ObjectPlacing/ObjectPlaced
Triggered when an object is being placed in a specific location (`UxrGrabManager.ObjectPlacing`) and once the object has been placed (`UxrGrabManager.ObjectPlaced`).

### ObjectRemoving/ObjectRemoved
Triggered when an object is being removed from its location (`UxrGrabManager.ObjectRemoving`) and once the object is removed (`UxrGrabManager.ObjectRemoved`).

### AnchorRangeEntering/AnchorRangeLeft
Triggered when an object enters (`UxrGrabManager.AnchorRangeEntering`) or leaves (`UxrGrabManager.AnchorRangeLeft`) the proximity of an anchor.

### PlacedObjectRangeEntered/PlacedObjectRangeLeft
Triggered when a placed object enters (`UxrGrabManager.PlacedObjectRangeEntered`) or leaves (`UxrGrabManager.PlacedObjectRangeLeft`) a defined range.

## `UxrGrabbableObject` Events
These events are raised for a specific [UxrGrabbableObject](/docs/programming-guide/manipulation/uxrgrabbableobject). They also receive a `UxrManipulationEventArgs` object, which will contain specific manipulation information depending on the event.
Check the [UxrGrabbableObject Event API Reference](/api/T_UltimateXR_Manipulation_UxrGrabbableObject#events) to see how these properties are used.

### ConstraintsApplying/ConstraintsApplied/ConstraintsFinished

### Grabbing/Grabbed

### Releasing/Released

### Placing/Placed

## `UxrGrabbableObjectAnchor` Events

### Placing/Placed

### Removing/Removed

### Removing/Removed

### SmoothPlaceTransitionEnded

## [UxrGrabbableObjectComponent](/docs/programming-guide/manipulation/uxrgrabbableobjectcomponent) Events

The base `UxrGrabbableObjectComponent` class can be used as a foundation to implement manipulation logic in a convenient way. Instead of subscribing and unsubscribing to events, you simply override methods.

For more details on how to implement this, check the [UxrGrabbableObjectComponent Programming Guide](/docs/programming-guide/manipulation/uxrgrabbableobjectcomponent).
