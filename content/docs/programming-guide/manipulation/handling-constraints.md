---
title: "Handling Constraints"
---

# Handling Constraints

In the context of grabbable objects, constraints are rules or limits that control how an object can be manipulated, both in terms of movement and rotation. They are essential in VR and interaction systems to create realistic behavior, such as limiting how far an object can be moved or rotated during manipulation.

The event system in UltimateXR provides access to the updating stage where constraints are applied, allowing for features like:
- Implementing custom constraints.
- Applying shaking effects to the `Transform` of a grabbed object.
- Visualizing the real hand’s position when the distance from the constrained hand exceeds a set threshold.

## Built-in Constraints

UltimateXR provides built-in support for constraints, allowing developers to specify linear and rotational limits directly on grabbable objects.

These constraints can be edited directly in the Constraints section of the [UxrGrabbableObject](/docs/manipulation/uxrgrabbableobject) component inspector.
![](/media/docs/programming-guide/manipulation/handling-constraints/ComponentConstraints.png)

They can also be visualized through gizmos in the Scene Window, giving you a clear representation of how the constraints will affect the object's movement and rotation in real-time.
![](/media/docs/programming-guide/manipulation/handling-constraints/ConstraintGizmos.png)

## Constraint Events

Although built-in constraints are versatile, there may be cases where custom constraints are needed to for more complex or unique object behavior.

Additionally, access to constraining data can be useful for visualization or applying effects to objects, such as shaking or other movement-based dynamics.

In UltimateXR, constraints can be handled using various `UxrGrabbableObject` events. These events allow developers to access and modify object behavior during manipulation.
Using events instead of the component’s `Update()` method ensures that `Transform` changes occur at the correct stage in the manipulation workflow.

{{% callout info %}}
Constraint events are raised only while the object is being manipulated, even when no built-in constraints are configured. This means you can still process constraint-related events without needing to define any specific constraints on the component inspector.
{{% /callout %}}

All constraint events receive an `UxrApplyConstraintsEventArgs` as a parameter. Currently, this object does not contain any meaningful data but may be expanded in future versions to include additional information.

### `UxrGrabbableObject.ConstraintsApplying`

This event is raised just before applying the built-in position and rotation constraints to the object. It can be used to store unconstrained `Transform` values.

Example that prints the unconstrained position of an object each frame:
```c#
class MyConstraintHandler : MonoBehaviour
{
	[SerializeField] private UxrGrabbableObject _grabbableObject;
	
	private void OnEnable()
	{
		// Subscribe to event
		_grabbableObject.ConstraintsApplying += GrabbableObject_ConstraintsApplying;
	}

	private void OnDisable()
	{
		// Unsubscribe from event
		_grabbableObject.ConstraintsApplying -= GrabbableObject_ConstraintsApplying;
	}
	
	// This is the event handling method.
	private void GrabbableObject_ConstraintsApplying(object sender, UxrApplyConstraintsEventArgs e)
	{
		Debug.Log($"Object {e.GrabbableObject.name} unconstrained position: {e.GrabbableObject.transform.position}");
	}
}
```

### `UxrGrabbableObject.ConstraintsApplied`

This event is raised after the built-in constraints are applied, which can be used to apply our own custom constraints.

Example that keeps an object's y position always above the ground:
```c#
class MyConstraintHandler : MonoBehaviour
{
	[SerializeField] private UxrGrabbableObject _grabbableObject;
	
	private void OnEnable()
	{
		// Subscribe to event
		_grabbableObject.ConstraintsApplying += GrabbableObject_ConstraintsApplying;
	}

	private void OnDisable()
	{
		// Unsubscribe from event
		_grabbableObject.ConstraintsApplying -= GrabbableObject_ConstraintsApplying;
	}
	
	// This is the event handling method.
	private void GrabbableObject_ConstraintsApplying(object sender, UxrApplyConstraintsEventArgs e)
	{
		Vector3 position = _grabbableObject.transform.position;
		position.y = Mathf.Abs(position.y);
		_grabbableObject.transform.position = position;
	}
}
```

### `UxrGrabbableObject.ConstraintsFinished`

This event is raised once `UxrGrabbableObject.ConstraintsApplied` has executed, enabling post-processing even when multiple custom constraints are in place.

A common use is to compute the distance between the unconstrained object position and the position after all the constraints have been applied. When this distance exceeds a set threshold, a transparent hand can be visualized to provide a visual cue of where your real hand is in the physical world. This helps maintain spatial awareness during interactions.

Example that prints the distance between the constrained and unconstrained position of an object each frame.
```c#
class MyConstraintHandler : MonoBehaviour
{
	[SerializeField] private UxrGrabbableObject _grabbableObject;
	
	private void OnEnable()
	{
		// Subscribe to event
		_grabbableObject.ConstraintsApplying += GrabbableObject_ConstraintsApplying;
		_grabbableObject.ConstraintsFinished += GrabbableObject_ConstraintsFinished;
	}

	private void OnDisable()
	{
		// Unsubscribe from event
		_grabbableObject.ConstraintsApplying -= GrabbableObject_ConstraintsApplying;
		_grabbableObject.ConstraintsFinished -= GrabbableObject_ConstraintsFinished;
	}
	
	private void GrabbableObject_ConstraintsApplying(object sender, UxrApplyConstraintsEventArgs e)
	{
		_unconstrainedPos = e.GrabbableObject.transform.position;
	}
	
	private void GrabbableObject_ConstraintsFinished(object sender, UxrApplyConstraintsEventArgs e)
	{
		Debug.Log($"Object {e.GrabbableObject.name} unconstrained-constrained distance: {Vector3.Distance(e.GrabbableObject.transform.position, _unconstrainedPos)}");
	}
	
	private Vector3 _unconstrainedPos;
}
```
