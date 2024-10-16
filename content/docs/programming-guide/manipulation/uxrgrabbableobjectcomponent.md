---
title: "UxrGrabbableObjectComponent"
---

# UxrGrabbableObjectComponent

## Introduction
The `UxrGrabbableObjectComponent` class is a base class designed to simplify the process of handling manipulation events in UltimateXR. It provides a convenient framework to react to object interactions using method overriding, minimizing code complexity.

{{% callout info %}}
The `UxrGrabbableObject` that the component processes events from must be present in the same GameObject.
{{% /callout %}}

## Inheritance
This component inherits from [UxrComponent](/docs/programming-guide/architecture/uxrcomponent), which offers additional functionality like [state serialization and synchronization](/docs/programming-guide/state-serialization-and-synchronization/introduction).

## Event Handling With Method Overriding
Unlike the traditional event subscription method, `UxrGrabbableObjectComponent` uses method overriding for event handling. This reduces the amount of code required to manage events such as grabbing, releasing, and placing objects. Simply override methods like `OnObjectGrabbed` or `OnObjectReleased` to define the behavior of your component.

Example:

```c#
public class MyComponent : UxrGrabbableObjectComponent<MyComponent>
{
    protected override void OnObjectGrabbed(UxrManipulationEventArgs e)
    {
        Debug.Log("Grabbed");
    }

    protected override void OnObjectReleased(UxrManipulationEventArgs e)
    {
        Debug.Log("Released");
    }
}
```

## Full Event List

Here is an example that shows the full list of events that can be overridden, outputting descriptive log messages for each event:

```c#
public class MyComponent : UxrGrabbableObjectComponent<MyComponent>
{
    protected override void OnObjectGrabbing(UxrManipulationEventArgs e)
    {
        Debug.Log($"Object {e.GrabbableObject.name} is about to be grabbed by avatar {e.Grabber.Avatar.name}");
    }

    protected override void OnObjectGrabbed(UxrManipulationEventArgs e)
    {
        Debug.Log($"Object {e.GrabbableObject.name} was grabbed by avatar {e.Grabber.Avatar.name}");
    }

    protected override void OnObjectReleasing(UxrManipulationEventArgs e)
    {
        Debug.Log($"Object {e.GrabbableObject.name} is about to be released by avatar {e.Grabber.Avatar.name}");
    }

    protected override void OnObjectReleased(UxrManipulationEventArgs e)
    {
        Debug.Log($"Object {e.GrabbableObject.name} was released by avatar {e.Grabber.Avatar.name}");
    }

    protected override void OnObjectPlacing(UxrManipulationEventArgs e)
    {
        Debug.Log($"Object {e.GrabbableObject.name} is about to be placed on anchor {e.GrabbableAnchor.name} by avatar {e.Grabber.Avatar.name}");
    }

    protected override void OnObjectPlaced(UxrManipulationEventArgs e)
    {
        Debug.Log($"Object {e.GrabbableObject.name} was placed on anchor {e.GrabbableAnchor.name} by avatar {e.Grabber.Avatar.name}");
    }

    protected override void OnObjectConstraintsApplying(UxrApplyConstraintsEventArgs e)
    {
        Debug.Log($"Object {e.GrabbableObject.name} is about to be constrained (if required)");
    }

    protected override void OnObjectConstraintsApplied(UxrApplyConstraintsEventArgs e)
    {
        Debug.Log($"Object {e.GrabbableObject.name} was constrained and can now be constrained using user specific code");
    }

    protected override void OnObjectConstraintsFinished(UxrApplyConstraintsEventArgs e)
    {
        Debug.Log($"All built-in and custom constraints were applied on object object {e.GrabbableObject.name}");
    }
}
```