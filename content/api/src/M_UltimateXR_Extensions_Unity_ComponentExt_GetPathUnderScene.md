# ComponentExt.GetPathUnderScene Method 
 

Gets the full path under current scene, including all parents, but scene name, for the given component.

**Namespace:**&nbsp;<a href="N_UltimateXR_Extensions_Unity">UltimateXR.Extensions.Unity</a><br />**Assembly:**&nbsp;UltimateXR (in UltimateXR.dll) Version: 0.0.0.0

## Syntax

**C#**<br />
``` C#
public static string GetPathUnderScene(
	this Component self
)
```


#### Parameters
&nbsp;<dl><dt>self</dt><dd>Type: Component<br />Component to get the path for</dd></dl>

#### Return Value
Type: <a href="https://docs.microsoft.com/dotnet/api/system.string" target="_blank" rel="noopener noreferrer">String</a><br />Component path string

#### Usage Note
In Visual Basic and C#, you can call this method as an instance method on any object of type Component. When you use instance method syntax to call this method, omit the first parameter. For more information, see <a href="https://docs.microsoft.com/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods" target="_blank" rel="noopener noreferrer">Extension Methods (Visual Basic)</a> or <a href="https://docs.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/extension-methods" target="_blank" rel="noopener noreferrer">Extension Methods (C# Programming Guide)</a>.

## Remarks
The path generated might not be unique. If that is the purpose, use <a href="M_UltimateXR_Extensions_Unity_ComponentExt_GetUniqueScenePath">GetUniqueScenePath(Component)</a> instead.

## See Also


#### Reference
<a href="T_UltimateXR_Extensions_Unity_ComponentExt">ComponentExt Class</a><br /><a href="N_UltimateXR_Extensions_Unity">UltimateXR.Extensions.Unity Namespace</a><br />