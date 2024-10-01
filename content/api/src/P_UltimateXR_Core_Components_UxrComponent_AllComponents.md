# UxrComponent.AllComponents Property 
 

Gets all the components, enabled or not, in all open scenes.

**Namespace:**&nbsp;<a href="N_UltimateXR_Core_Components">UltimateXR.Core.Components</a><br />**Assembly:**&nbsp;UltimateXR (in UltimateXR.dll) Version: 0.0.0.0

## Syntax

**C#**<br />
``` C#
public static IEnumerable<UxrComponent> AllComponents { get; }
```


#### Property Value
Type: <a href="https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1" target="_blank" rel="noopener noreferrer">IEnumerable</a>(<a href="T_UltimateXR_Core_Components_UxrComponent">UxrComponent</a>)

## Remarks
Components that have never been enabled are not returned. Components are automatically registered through their Awake() call, which is never called if the object has never been enabled. In this case it is recommended to resort to GetComponentsInChildren``1(Boolean) or FindObjectsOfType``1(Boolean).

## See Also


#### Reference
<a href="T_UltimateXR_Core_Components_UxrComponent">UxrComponent Class</a><br /><a href="N_UltimateXR_Core_Components">UltimateXR.Core.Components Namespace</a><br />