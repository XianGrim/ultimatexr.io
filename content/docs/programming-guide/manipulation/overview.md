---
title: "Manipulation Programming Guide"
---

# Overview

The **manipulation system** in UltimateXR enables avatars to interact with objects in VR environments. It provides a variety of tools and components to manage how avatars can grab, move, rotate, and manipulate objects in a realistic and natural way.

This guide offers a programmatic perspective. For detailed instructions on setting up components in Unity, please refer to the [Manipulation User Guide](/docs/manipulation/overview). You can also check the [Manipulation API Reference](/api/N_UltimateXR_Manipulation).

## Key Components

The manipulation system relies on four key components, which work together to enable object interaction in VR:

### [UxrGrabber](/docs/programming-guide/manipulation/uxrgrabber)

The `UxrGrabber` component is added to the avatar's hands, allowing them to grab objects in the scene.

### [UxrGrabbableObject](/docs/programming-guide/manipulation/uxrgrabbableobject)

Objects that can be manipulated have the `UxrGrabbableObject` component. This defines how an object behaves when grabbed, including setting movement constraints, rotation limits, and snap points for alignment when interacting with avatars.

### [UxrGrabbableObjectAnchor](/docs/programming-guide/manipulation/uxrgrabbableobjectanchor)

The `UxrGrabbableObjectAnchor` component is added to specific GameObjects where grabbables can be snapped to.

### [UxrGrabManager](/docs/programming-guide/manipulation/uxrgrabmanager)

The `UxrGrabManager` component is a singleton in the scene that manages all grab interactions between avatars and grabbable objects. It provides functionality to create manipulations programmatically and includes events to respond to specific interaction changes.

## Other Components

These components provide additional functionality and extensibility:

### [UxrGrabbableObjectComponent](/docs/programming-guide/manipulation/uxrgrabbableobjectcomponent)

Base class for creating components that interact with a `UxrGrabbableObject`. It simplifies the handling of manipulation events by allowing you to override methods, eliminating the need for manual event subscription.

### [UxrGrabPointShape](/docs/programming-guide/manipulation/uxrgrabpointshape)

Base class for extending grab points on objects to support more complex shapes. This allows to create grabbable objects like cylinders, boxes, and spheres, which can be grabbed from any point and angle, rather than just a single defined spot.
For example, the `UxrGrabPointAxisAngle` component enables the manipulation of cylindrical shapes.