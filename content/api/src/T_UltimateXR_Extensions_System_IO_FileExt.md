# FileExt Class
 

File extensions.


## Inheritance Hierarchy
<a href="https://docs.microsoft.com/dotnet/api/system.object" target="_blank" rel="noopener noreferrer">System.Object</a><br />&nbsp;&nbsp;UltimateXR.Extensions.System.IO.FileExt<br />
**Namespace:**&nbsp;<a href="N_UltimateXR_Extensions_System_IO">UltimateXR.Extensions.System.IO</a><br />**Assembly:**&nbsp;UltimateXR (in UltimateXR.dll) Version: 0.0.0.0

## Syntax

**C#**<br />
``` C#
public static class FileExt
```

<a href="UltimateXR/Scripts/Extensions/System/IO/FileExt.cs" rel="noopener noreferrer" title="View the source code">View Source</a><br />
The FileExt type exposes the following members.


## Methods
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Extensions_System_IO_FileExt_Read">Read</a></td><td>
Reads bytes from a file asynchronously. Multiple file locations are supported:
&nbsp;<ul><li>Files in streamingAssetsPath</li><li>Files in an http:// location</li><li>Files in a file:// location</li></ul>&nbsp;
All other Uris will be considered file paths and the file:// location will be added.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Extensions_System_IO_FileExt_ReadText">ReadText</a></td><td>
Reads text from a file asynchronously. Multiple file locations are supported:
&nbsp;<ul><li>Files in streamingAssetsPath</li><li>Files in an http:// location</li><li>Files in a file:// location</li></ul>&nbsp;
All other Uris will be considered file paths and the file:// location will be added.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Extensions_System_IO_FileExt_TryReadText">TryReadText</a></td><td>
Reads text from a file asynchronously. Multiple file locations are supported:
&nbsp;<ul><li>Files in streamingAssetsPath</li><li>Files in an http:// location</li><li>Files in a file:// location</li></ul>&nbsp;
All other Uris will be considered file paths and the file:// location will be added.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Extensions_System_IO_FileExt_Write">Write(Byte[], String, CancellationToken)</a></td><td>
Asynchronously writes an <a href="https://docs.microsoft.com/dotnet/api/system.array" target="_blank" rel="noopener noreferrer">Array</a> of <a href="https://docs.microsoft.com/dotnet/api/system.byte" target="_blank" rel="noopener noreferrer">Byte</a> to a file at *path*.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Extensions_System_IO_FileExt_Write_1">Write(String, Stream, CancellationToken)</a></td><td>
Asynchronously writes the content of an *sourceStream* to a file at *path*.</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")![Static member](media/static.gif "Static member")</td><td><a href="M_UltimateXR_Extensions_System_IO_FileExt_WriteText">WriteText</a></td><td>
Asynchronously writes text to a file location.</td></tr></table>&nbsp;
<a href="#fileext-class">Back to Top</a>

## See Also


#### Reference
<a href="N_UltimateXR_Extensions_System_IO">UltimateXR.Extensions.System.IO Namespace</a><br />