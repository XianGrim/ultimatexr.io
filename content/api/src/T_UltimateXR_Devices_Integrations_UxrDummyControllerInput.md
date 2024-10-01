# UxrDummyControllerInput Class
 

Dummy input class that is used when there is no active input component in the avatar. It has the advantage of avoiding to check for null input component and it doesn't generate any type of input events.


## Inheritance Hierarchy
<a href="https://docs.microsoft.com/dotnet/api/system.object" target="_blank" rel="noopener noreferrer">System.Object</a><br />&nbsp;&nbsp;Object<br />&nbsp;&nbsp;&nbsp;&nbsp;Component<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Behaviour<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MonoBehaviour<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="T_UltimateXR_Core_Components_UxrComponent">UltimateXR.Core.Components.UxrComponent</a><br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="T_UltimateXR_Core_Components_UxrComponent_1">UltimateXR.Core.Components.UxrComponent</a>(<a href="T_UltimateXR_Devices_UxrControllerInput">UxrControllerInput</a>)<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="T_UltimateXR_Core_Components_Composite_UxrAvatarComponent_1">UltimateXR.Core.Components.Composite.UxrAvatarComponent</a>(<a href="T_UltimateXR_Devices_UxrControllerInput">UxrControllerInput</a>)<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="T_UltimateXR_Devices_UxrControllerInput">UltimateXR.Devices.UxrControllerInput</a><br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UltimateXR.Devices.Integrations.UxrDummyControllerInput<br />
**Namespace:**&nbsp;<a href="N_UltimateXR_Devices_Integrations">UltimateXR.Devices.Integrations</a><br />**Assembly:**&nbsp;UltimateXR (in UltimateXR.dll) Version: 0.0.0.0

## Syntax

**C#**<br />
``` C#
public class UxrDummyControllerInput : UxrControllerInput
```

<a href="UltimateXR/Scripts/Devices/Integrations/UxrDummyControllerInput.cs" rel="noopener noreferrer" title="View the source code">View Source</a><br />
The UxrDummyControllerInput type exposes the following members.


## Constructors
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_Integrations_UxrDummyControllerInput__ctor">UxrDummyControllerInput</a></td><td /></tr></table>&nbsp;
<a href="#uxrdummycontrollerinput-class">Back to Top</a>

## Properties
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="P_UltimateXR_Devices_Integrations_UxrDummyControllerInput_IsHandednessSupported">IsHandednessSupported</a></td><td>

Gets whether <a href="P_UltimateXR_Devices_IUxrControllerInput_Handedness">Handedness</a> can be used. In <a href="T_UltimateXR_Devices_UxrControllerSetupType">Single</a> devices, it may be used to control which hand is holding the controller. In <a href="T_UltimateXR_Devices_UxrControllerSetupType">Dual</a> devices it is used to determine which hands have the <a href="P_UltimateXR_Devices_IUxrControllerInput_Primary">Primary</a> (dominant) and <a href="P_UltimateXR_Devices_IUxrControllerInput_Secondary">Secondary</a> (non-dominant) roles.
 Devices such as gamepads don't support handedness and will target the single device no matter which <a href="T_UltimateXR_Core_UxrHandSide">UxrHandSide</a> is used. In this case it is good practice to use <a href="P_UltimateXR_Devices_IUxrControllerInput_Primary">Primary</a> to target the device in order to make the code cleaner.
 (Overrides <a href="P_UltimateXR_Devices_UxrControllerInput_IsHandednessSupported">UxrControllerInput.IsHandednessSupported</a>.)</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="P_UltimateXR_Devices_Integrations_UxrDummyControllerInput_LeftControllerName">LeftControllerName</a></td><td>
Gets the left controller name, or empty if not connected / doesn't exist. In <a href="T_UltimateXR_Devices_UxrControllerSetupType">Single</a> configurations where <a href="P_UltimateXR_Devices_IUxrControllerInput_IsHandednessSupported">IsHandednessSupported</a> is not available, both sides will return the same name.
 (Overrides <a href="P_UltimateXR_Devices_UxrControllerInput_LeftControllerName">UxrControllerInput.LeftControllerName</a>.)</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="P_UltimateXR_Devices_Integrations_UxrDummyControllerInput_RightControllerName">RightControllerName</a></td><td>
Gets the right controller name, or empty if not connected / doesn't exist. In <a href="T_UltimateXR_Devices_UxrControllerSetupType">Single</a> configurations where <a href="P_UltimateXR_Devices_IUxrControllerInput_IsHandednessSupported">IsHandednessSupported</a> is not available, both sides will return the same name.
 (Overrides <a href="P_UltimateXR_Devices_UxrControllerInput_RightControllerName">UxrControllerInput.RightControllerName</a>.)</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="P_UltimateXR_Devices_Integrations_UxrDummyControllerInput_SetupType">SetupType</a></td><td>
Gets the setup type. See <a href="T_UltimateXR_Devices_UxrControllerSetupType">UxrControllerSetupType</a>.
 (Overrides <a href="P_UltimateXR_Devices_UxrControllerInput_SetupType">UxrControllerInput.SetupType</a>.)</td></tr></table>&nbsp;
<a href="#uxrdummycontrollerinput-class">Back to Top</a>

## Methods
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_Integrations_UxrDummyControllerInput_GetControllerCapabilities">GetControllerCapabilities</a></td><td>
Gets the capabilities of the XR controller.
 (Overrides <a href="M_UltimateXR_Devices_UxrControllerInput_GetControllerCapabilities">UxrControllerInput.GetControllerCapabilities(UxrHandSide)</a>.)</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_Integrations_UxrDummyControllerInput_GetInput1D">GetInput1D</a></td><td>
Gets the state of an analog controller input element.
 (Overrides <a href="M_UltimateXR_Devices_UxrControllerInput_GetInput1D">UxrControllerInput.GetInput1D(UxrHandSide, UxrInput1D, Boolean)</a>.)</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_Integrations_UxrDummyControllerInput_GetInput2D">GetInput2D</a></td><td>
Gets the state of a 2D input element (joystick, touchpad...).
 (Overrides <a href="M_UltimateXR_Devices_UxrControllerInput_GetInput2D">UxrControllerInput.GetInput2D(UxrHandSide, UxrInput2D, Boolean)</a>.)</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_Integrations_UxrDummyControllerInput_HasControllerElements">HasControllerElements</a></td><td>
Checks if the given controller has specific elements.
 (Overrides <a href="M_UltimateXR_Devices_UxrControllerInput_HasControllerElements">UxrControllerInput.HasControllerElements(UxrHandSide, UxrControllerElements)</a>.)</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_Integrations_UxrDummyControllerInput_IsControllerEnabled">IsControllerEnabled</a></td><td>
Checks whether the given controller is enabled.
 (Overrides <a href="M_UltimateXR_Devices_UxrControllerInput_IsControllerEnabled">UxrControllerInput.IsControllerEnabled(UxrHandSide)</a>.)</td></tr></table>&nbsp;
<a href="#uxrdummycontrollerinput-class">Back to Top</a>

## Extension Methods
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public Extension Method](media/pubextension.gif "Public Extension Method")</td><td><a href="M_UltimateXR_Extensions_Unity_MonoBehaviourExt_CheckSetEnabled">CheckSetEnabled</a></td><td>
Enables/disabled the component if it isn't enabled already.
 (Defined by <a href="T_UltimateXR_Extensions_Unity_MonoBehaviourExt">MonoBehaviourExt</a>.)</td></tr><tr><td>![Public Extension Method](media/pubextension.gif "Public Extension Method")</td><td><a href="M_UltimateXR_Extensions_Unity_ComponentExt_GetOrAddComponent__1">GetOrAddComponent(T)</a></td><td>
Gets the Component of a given type. If it doesn't exist, it is added to the GameObject.
 (Defined by <a href="T_UltimateXR_Extensions_Unity_ComponentExt">ComponentExt</a>.)</td></tr><tr><td>![Public Extension Method](media/pubextension.gif "Public Extension Method")</td><td><a href="M_UltimateXR_Extensions_Unity_ComponentExt_GetPathUnderScene">GetPathUnderScene</a></td><td>
Gets the full path under current scene, including all parents, but scene name, for the given component.
 (Defined by <a href="T_UltimateXR_Extensions_Unity_ComponentExt">ComponentExt</a>.)</td></tr><tr><td>![Public Extension Method](media/pubextension.gif "Public Extension Method")</td><td><a href="M_UltimateXR_Extensions_Unity_ComponentExt_GetSceneUid">GetSceneUid</a></td><td>
Gets an unique identifier string for the given component.
 (Defined by <a href="T_UltimateXR_Extensions_Unity_ComponentExt">ComponentExt</a>.)</td></tr><tr><td>![Public Extension Method](media/pubextension.gif "Public Extension Method")</td><td><a href="M_UltimateXR_Extensions_Unity_ComponentExt_GetUniqueScenePath">GetUniqueScenePath</a></td><td>
Gets an unique path in the scene for the given component. It will include scene name, sibling and component indices to make it unique.
 (Defined by <a href="T_UltimateXR_Extensions_Unity_ComponentExt">ComponentExt</a>.)</td></tr><tr><td>![Public Extension Method](media/pubextension.gif "Public Extension Method")</td><td><a href="M_UltimateXR_Extensions_Unity_MonoBehaviourExt_LoopCoroutine">LoopCoroutine</a></td><td>
Creates a coroutine that simplifies executing a loop during a certain amount of time.
 (Defined by <a href="T_UltimateXR_Extensions_Unity_MonoBehaviourExt">MonoBehaviourExt</a>.)</td></tr><tr><td>![Public Extension Method](media/pubextension.gif "Public Extension Method")</td><td><a href="M_UltimateXR_Extensions_Unity_ComponentExt_SafeGetComponentInParent__1">SafeGetComponentInParent(T)</a></td><td>
Gets the Component of a given type in the GameObject or any of its parents. It also works on prefabs, where regular GetComponentInParent(Type, Boolean) will not work: https://issuetracker.unity3d.com/issues/getcomponentinparent-is-returning-null-when-the-gameobject-is-a-prefab
 (Defined by <a href="T_UltimateXR_Extensions_Unity_ComponentExt">ComponentExt</a>.)</td></tr><tr><td>![Public Extension Method](media/pubextension.gif "Public Extension Method")</td><td><a href="M_UltimateXR_Extensions_Unity_ObjectExt_ShowInInspector">ShowInInspector(Boolean)</a></td><td>Overloaded.  
Controls whether to show the current object in the inspector.
 (Defined by <a href="T_UltimateXR_Extensions_Unity_ObjectExt">ObjectExt</a>.)</td></tr><tr><td>![Public Extension Method](media/pubextension.gif "Public Extension Method")</td><td><a href="M_UltimateXR_Extensions_Unity_ObjectExt_ShowInInspector_1">ShowInInspector(Boolean, Boolean)</a></td><td>Overloaded.  
Controls whether to show the current object in the inspector and whether it is editable.
 (Defined by <a href="T_UltimateXR_Extensions_Unity_ObjectExt">ObjectExt</a>.)</td></tr><tr><td>![Public Extension Method](media/pubextension.gif "Public Extension Method")</td><td><a href="M_UltimateXR_Extensions_System_ObjectExt_ThrowIfNull">ThrowIfNull</a></td><td>
Throws an exception if the object is null.
 (Defined by <a href="T_UltimateXR_Extensions_System_ObjectExt">ObjectExt</a>.)</td></tr></table>&nbsp;
<a href="#uxrdummycontrollerinput-class">Back to Top</a>

## See Also


#### Reference
<a href="N_UltimateXR_Devices_Integrations">UltimateXR.Devices.Integrations Namespace</a><br />