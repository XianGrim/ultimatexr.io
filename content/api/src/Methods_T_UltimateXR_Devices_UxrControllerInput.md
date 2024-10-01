# UxrControllerInput Methods
 

The <a href="T_UltimateXR_Devices_UxrControllerInput">UxrControllerInput</a> type exposes the following members.


## Methods
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_AreAllControllerElementsBlinking">AreAllControllerElementsBlinking</a></td><td>
Checks if all elements of a specific controller element are currently blinking</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_Awake">Awake</a></td><td>
Initializes internal data
 (Overrides <a href="M_UltimateXR_Core_Components_Composite_UxrAvatarComponent_1_Awake">UxrAvatarComponent(T).Awake()</a>.)</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_ButtonToControllerElement">ButtonToControllerElement</a></td><td>
Gets the controller element (<a href="T_UltimateXR_Devices_UxrControllerElements">UxrControllerElements</a>) enum value given a controller button ( <a href="T_UltimateXR_Devices_UxrInputButtons">UxrInputButtons</a>) enum value.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_ControllerElementToButton">ControllerElementToButton</a></td><td>
Gets the controller button (<a href="T_UltimateXR_Devices_UxrInputButtons">UxrInputButtons</a>) enum value given a controller element ( <a href="T_UltimateXR_Devices_UxrControllerElements">UxrControllerElements</a>) enum value.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_ControllerElementToInput1D">ControllerElementToInput1D</a></td><td>
Gets the <a href="T_UltimateXR_Devices_UxrInput1D">UxrInput1D</a> enum value given a controller element (<a href="T_UltimateXR_Devices_UxrControllerElements">UxrControllerElements</a> ) enum value.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_ControllerElementToInput2D">ControllerElementToInput2D</a></td><td>
Gets the <a href="T_UltimateXR_Devices_UxrInput2D">UxrInput2D</a> enum value given a controller element (<a href="T_UltimateXR_Devices_UxrControllerElements">UxrControllerElements</a> ) enum value.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_FilterTwoAxesDeadZone">FilterTwoAxesDeadZone</a></td><td>
Filters a two-axis input using a dead-zone. Values inside the dead-zone will remain (0.0, 0.0).</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonFlags">GetButtonFlags</a></td><td>
Gets flags representing the current button state</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonPressFlags">GetButtonPressFlags</a></td><td>
Gets an uint value representing press states for each the controller <a href="T_UltimateXR_Devices_UxrInputButtons">UxrInputButtons</a> flags in the current frame.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonPressFlagsLastFrame">GetButtonPressFlagsLastFrame</a></td><td>
Gets an uint value representing press states for each the in the last frame.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsEvent">GetButtonsEvent</a></td><td>
Checks if a given input event took place for a button or all buttons in a set in the current frame.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsEventAny">GetButtonsEventAny</a></td><td>
Checks if a given input event took place for a button or any button in a set in the current frame.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsPress">GetButtonsPress</a></td><td>
Checks if the given button or buttons are being pressed in the current frame.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsPressAny">GetButtonsPressAny</a></td><td>
Checks if the given button or any button in a set is being pressed in the current frame.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsPressDown">GetButtonsPressDown</a></td><td>
Checks if the given button or buttons are being pressed in the current frame but weren't the previous frame (press-down).</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsPressDownAny">GetButtonsPressDownAny</a></td><td>
Checks if the given button or any button in a set is being pressed in the current frame but wasn't the previous frame (press-down).</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsPressUp">GetButtonsPressUp</a></td><td>
Checks if the given button or buttons aren't being pressed in the current frame but were during the previous frame (release press).</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsPressUpAny">GetButtonsPressUpAny</a></td><td>
Checks if the given button or any button in a set isn't being pressed in the current frame but was during the previous frame (release press).</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsTouch">GetButtonsTouch</a></td><td>
Checks if the given button or all buttons in a set are being touched in the current frame.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsTouchAny">GetButtonsTouchAny</a></td><td>
Checks if the given button or any button in a set is being touched in the current frame.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsTouchDown">GetButtonsTouchDown</a></td><td>
Checks if the given button or buttons are being touched in the current frame but weren't the previous frame (touch-down).</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsTouchDownAny">GetButtonsTouchDownAny</a></td><td>
Checks if the given button or any button in a set is being touched in the current frame but not in the previous frame (touch-down).</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsTouchUp">GetButtonsTouchUp</a></td><td>
Checks if the given button or buttons aren't being touched in the current frame but were during the previous frame (release touch).</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonsTouchUpAny">GetButtonsTouchUpAny</a></td><td>
Checks if the given button or any button in a set isn't being touched in the current frame but was during the previous frame (release touch).</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonTouchFlags">GetButtonTouchFlags</a></td><td>
Gets an uint value representing touch states for each the controller <a href="T_UltimateXR_Devices_UxrInputButtons">UxrInputButtons</a> flags in the current frame.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetButtonTouchFlagsLastFrame">GetButtonTouchFlagsLastFrame</a></td><td>
Gets an uint value representing touch states for each the controller <a href="T_UltimateXR_Devices_UxrInputButtons">UxrInputButtons</a> flags in the last frame.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetController3DModel">GetController3DModel</a></td><td>
Gets the instanced controller 3D model for a given hand.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetControllerCapabilities">GetControllerCapabilities</a></td><td>
Gets the capabilities of the XR controller.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetControllerElementsGameObjects">GetControllerElementsGameObjects</a></td><td>
Returns a list of GameObjects that represent parts of the instantiated controller. This can be useful to highlight buttons or other elements during tutorials. Functionality to make these elements blink is also provided by the framework.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetIgnoreControllerInput">GetIgnoreControllerInput</a></td><td>
Gets whether the given controller input should be ignored.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetInput1D">GetInput1D</a></td><td>
Gets the state of an analog controller input element.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_GetInput2D">GetInput2D</a></td><td>
Gets the state of a 2D input element (joystick, touchpad...).</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_HasControllerElements">HasControllerElements</a></td><td>
Checks if the given controller has specific elements.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_Input1DToControllerElement">Input1DToControllerElement</a></td><td>
Gets the controller elements <a href="T_UltimateXR_Devices_UxrControllerElements">UxrControllerElements</a> enum value given a <a href="T_UltimateXR_Devices_UxrInput1D">UxrInput1D</a> enum value.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_Input2DToAngle">Input2DToAngle</a></td><td>
Transforms a two-axis input to an angle. 0 degrees is right and degrees increase counterclockwise.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_Input2DToControllerElement">Input2DToControllerElement</a></td><td>
Gets the controller elements <a href="T_UltimateXR_Devices_UxrControllerElements">UxrControllerElements</a> enum value given a <a href="T_UltimateXR_Devices_UxrInput2D">UxrInput2D</a> enum value.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_IsAnyControllerElementBlinking">IsAnyControllerElementBlinking</a></td><td>
Checks if any specific controller element is currently blinking</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_IsControllerEnabled">IsControllerEnabled</a></td><td>
Checks whether the given controller is enabled.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_IsInput2dDPadDown">IsInput2dDPadDown(Single)</a></td><td>
Checks if the given 2-axis input represented as an angle in degrees corresponds to a down press in a digital pad. 0 degrees is right and degrees increase counterclockwise.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_IsInput2dDPadDown_1">IsInput2dDPadDown(Vector2)</a></td><td>
Checks if the given 2-axis input corresponds to a down press in a digital pad.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_IsInput2dDPadLeft">IsInput2dDPadLeft(Single)</a></td><td>
Checks if the given 2-axis input represented as an angle in degrees corresponds to a left press in a digital pad. 0 degrees is right and degrees increase counterclockwise.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_IsInput2dDPadLeft_1">IsInput2dDPadLeft(Vector2)</a></td><td>
Checks if the given 2-axis input corresponds to a left press in a digital pad.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_IsInput2dDPadRight">IsInput2dDPadRight(Single)</a></td><td>
Checks if the given 2-axis input represented as an angle in degrees corresponds to a right press in a digital pad. 0 degrees is right and degrees increase counterclockwise.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_IsInput2dDPadRight_1">IsInput2dDPadRight(Vector2)</a></td><td>
Checks if the given 2-axis input corresponds to a right press in a digital pad.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_IsInput2dDPadUp">IsInput2dDPadUp(Single)</a></td><td>
Checks if the given 2-axis input represented as an angle in degrees corresponds to an up press in a digital pad. 0 degrees is right and degrees increase counterclockwise.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_IsInput2dDPadUp_1">IsInput2dDPadUp(Vector2)</a></td><td>
Checks if the given 2-axis input corresponds to an up press in a digital pad.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_OnButtonStateChanged">OnButtonStateChanged</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrControllerInput_ButtonStateChanged">ButtonStateChanged</a> event</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_OnDestroy">OnDestroy</a></td><td>
Sets events to null in order to help remove unused references
 (Overrides <a href="M_UltimateXR_Core_Components_UxrComponent_1_OnDestroy">UxrComponent(T).OnDestroy()</a>.)</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_OnDeviceConnected">OnDeviceConnected</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrControllerInput_DeviceConnected">DeviceConnected</a> event</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_OnHapticRequesting">OnHapticRequesting</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrControllerInput_HapticRequesting">HapticRequesting</a> event</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_OnInput1DChanged">OnInput1DChanged</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrControllerInput_Input1DChanged">Input1DChanged</a> event</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_OnInput2DChanged">OnInput2DChanged</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrControllerInput_Input2DChanged">Input2DChanged</a> event</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_OnUpdated">OnUpdated</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrControllerInput_Updated">Updated</a> event</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_OnUpdating">OnUpdating</a></td><td>
Event trigger for the <a href="E_UltimateXR_Devices_UxrControllerInput_Updating">Updating</a> event</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_SendGrabbableHapticFeedback">SendGrabbableHapticFeedback(UxrGrabbableObject, UxrHapticClip)</a></td><td>
Sends haptic feedback to XR controllers that are being used to manipulate a grabbable object. Each hand associated to an XR controller that is grabbing the object will receive haptic feedback.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_SendGrabbableHapticFeedback_1">SendGrabbableHapticFeedback(UxrGrabbableObject, UxrHapticClipType, Single, Single, UxrHapticMode)</a></td><td>
Sends haptic feedback to XR controllers that are being used to manipulate a grabbable object. Each hand associated to an XR controller that is grabbing the object will receive haptic feedback.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_SendHapticFeedback_1">SendHapticFeedback(UxrHandSide, UxrHapticClip)</a></td><td>
Sends haptic feedback to a controller if the controller supports it.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_SendHapticFeedback">SendHapticFeedback(UxrHandSide, Single, Single, Single, UxrHapticMode)</a></td><td>
Sends haptic feedback to a controller if the controller supports it.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_SendHapticFeedback_2">SendHapticFeedback(UxrHandSide, UxrHapticClipType, Single, Single, UxrHapticMode)</a></td><td>
Sends a predefined haptic clip to a controller.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_SetButtonFlags">SetButtonFlags</a></td><td>
Sets the given button flags</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_SetIgnoreControllerInput">SetIgnoreControllerInput</a></td><td>
Sets whether the given controller input should be ignored.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_ShouldIgnoreInput">ShouldIgnoreInput</a></td><td>
Checks whether the given hand input should be ignored.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_Start">Start</a></td><td>
Unity Start event
 (Overrides <a href="M_UltimateXR_Core_Components_UxrComponent_Start">UxrComponent.Start()</a>.)</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_StartControllerElementsBlinking">StartControllerElementsBlinking</a></td><td>
Starts blinking one or more elements in a controller. This can be useful during tutorials to highlight which button(s) to press.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_StopAllBlinking">StopAllBlinking</a></td><td>
Stops all controller elements to blink</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_StopControllerElementsBlinking">StopControllerElementsBlinking</a></td><td>
Stops controller elements to blink</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_StopHapticFeedback">StopHapticFeedback</a></td><td>
Stops all current haptics in a given controller.</td></tr><tr><td>![Protected method](media/protmethod.gif "Protected method")</td><td><a href="M_UltimateXR_Devices_UxrControllerInput_UpdateInput">UpdateInput</a></td><td>
Virtual method that should be overriden in child classes in order to update the current input state information (buttons and all the other elements in the controllers).</td></tr></table>&nbsp;
<a href="#uxrcontrollerinput-methods">Back to Top</a>

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
<a href="#uxrcontrollerinput-methods">Back to Top</a>

## See Also


#### Reference
<a href="T_UltimateXR_Devices_UxrControllerInput">UxrControllerInput Class</a><br /><a href="N_UltimateXR_Devices">UltimateXR.Devices Namespace</a><br />