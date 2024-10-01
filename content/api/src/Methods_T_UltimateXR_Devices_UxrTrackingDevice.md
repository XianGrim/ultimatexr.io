# UxrTrackingDevice Methods
 

The <a href="T_UltimateXR_Devices_UxrTrackingDevice">UxrTrackingDevice</a> type exposes the following members.


## Methods
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrTrackingDevice_GetHeadsetDevice">GetHeadsetDevice</a></td><td>
Tries to get the connected headset device.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrTrackingDevice_OnAvatarUpdated">OnAvatarUpdated</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrTrackingDevice_AvatarUpdated">AvatarUpdated</a> event. Can be used to override in child classes in order to use the event without subscribing to the parent.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrTrackingDevice_OnAvatarUpdating">OnAvatarUpdating</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrTrackingDevice_AvatarUpdating">AvatarUpdating</a> event. Can be used to override in child classes in order to use the event without subscribing to the parent.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrTrackingDevice_OnDestroy">OnDestroy</a></td><td>
Sets events to null in order to help remove unused references.
 (Overrides <a href="M_UltimateXR_Core_Components_UxrComponent_1_OnDestroy">UxrComponent(T).OnDestroy()</a>.)</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrTrackingDevice_OnDeviceConnected">OnDeviceConnected</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrTrackingDevice_DeviceConnected">DeviceConnected</a> event. Can be used to override in child classes in order to use the event without subscribing to the parent.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrTrackingDevice_OnSensorsUpdated">OnSensorsUpdated</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrTrackingDevice_SensorsUpdated">SensorsUpdated</a> event. Can be used to override in child classes in order to use the event without subscribing to the parent.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrTrackingDevice_OnSensorsUpdating">OnSensorsUpdating</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrTrackingDevice_SensorsUpdating">SensorsUpdating</a> event. Can be used to override in child classes in order to use the event without subscribing to the parent.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrTrackingDevice_UpdateAvatar">UpdateAvatar</a></td><td>
Overriden in child classes to implement the update of the avatar using the current sensor data.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrTrackingDevice_UpdateSensors">UpdateSensors</a></td><td>
Overriden in child classes to implement the update of the current sensor data.</td></tr></table>&nbsp;
<a href="#uxrtrackingdevice-methods">Back to Top</a>

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
<a href="#uxrtrackingdevice-methods">Back to Top</a>

## See Also


#### Reference
<a href="T_UltimateXR_Devices_UxrTrackingDevice">UxrTrackingDevice Class</a><br /><a href="N_UltimateXR_Devices">UltimateXR.Devices Namespace</a><br />