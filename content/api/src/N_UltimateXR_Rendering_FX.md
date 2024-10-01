# UltimateXR.Rendering.FX Namespace

## Classes
&nbsp;<table><tr><th></th><th>Class</th><th>Description</th></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="T_UltimateXR_Rendering_FX_UxrMagnifyingGlassUrp">UxrMagnifyingGlassUrp</a></td><td>
Component that renders a magnifying glass effect on an object, using the URP pipeline:
&nbsp;<ul><li>If the Glass Axes transform is not set, it will use the transform on the component's GameObject.</li><li>The magnifying glass normal is determined by the -forward axis, so the user will look through the glass pointing in the forward axis direction.</li><li>The component requires a Renderer on the same GameObject with a material compatible with the URP magnifying glass refraction. They can be found in the UltimateXR/FX/ category.</li></ul></td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="T_UltimateXR_Rendering_FX_UxrPlanarReflectionBrp">UxrPlanarReflectionBrp</a></td><td>
Component that renders a planar reflection image of the scene on an object, using the built-in render pipeline:
&nbsp;<ul><li>If the Mirror Transform is not set, it will use the transform on the component's GameObject.</li><li>The component requires a Renderer on the same GameObject with a material compatible with the BRP planar reflection. They can be found in the UltimateXR/FX/ category.</li><li>The mirror normal is determined by the -forward axis of Mirror Transform.</li></ul></td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="T_UltimateXR_Rendering_FX_UxrPlanarReflectionUrp">UxrPlanarReflectionUrp</a></td><td>
Component that renders a planar reflection image of the scene on an object, using the URP pipeline:
&nbsp;<ul><li>If either Mirror Transform or Mirror Renderer ar not set, it will try to get these components on the same GameObjects where the planar reflection is.</li><li>The mirror normal is determined by the -forward axis of Mirror Transform.</li><li>For some reason the reflection will not work if the clear skybox is not set on the camera. Unity doesn't seem to compute the projection matrices correctly.</li><li>The mirror renderer should have a material compatible with the URP planar reflection. They can be found in the UltimateXR/FX/ category.</li></ul></td></tr></table>&nbsp;