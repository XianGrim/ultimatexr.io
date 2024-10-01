# UxrPostUpdateMode Enumeration
 

Enumerates where <a href="T_UltimateXR_Core_UxrManager">UxrManager</a> updates the <a href="T_UltimateXR_Avatar_UxrAvatar">UxrAvatar</a> post-update. Among elements processed in the post-update is the animation. See <a href="P_UltimateXR_Core_UxrManager_PostUpdateMode">PostUpdateMode</a>

**Namespace:**&nbsp;<a href="N_UltimateXR_Core">UltimateXR.Core</a><br />**Assembly:**&nbsp;UltimateXR (in UltimateXR.dll) Version: 0.0.0.0

## Syntax

**C#**<br />
``` C#
public enum UxrPostUpdateMode
```

<a href="UltimateXR/Scripts/Core/UxrPostUpdateMode.cs" rel="noopener noreferrer" title="View the source code">View Source</a><br />

## Members
&nbsp;<table><tr><th></th><th>Member name</th><th>Value</th><th>Description</th></tr><tr><td /><td target="F:UltimateXR.Core.UxrPostUpdateMode.None">**None**</td><td>0</td><td>Don't update.</td></tr><tr><td /><td target="F:UltimateXR.Core.UxrPostUpdateMode.Update">**Update**</td><td>1</td><td>Update on <a href="T_UltimateXR_Core_UxrManager">UxrManager</a>'s Update(). If the <a href="T_UltimateXR_Avatar_UxrAvatar">UxrAvatar</a> has any Animator components, these will override any animation or hand poses generated by UltimateXR.</td></tr><tr><td /><td target="F:UltimateXR.Core.UxrPostUpdateMode.LateUpdate">**LateUpdate**</td><td>2</td><td>Update on <a href="T_UltimateXR_Core_UxrManager">UxrManager</a>'s LateUpdate(). If the <a href="T_UltimateXR_Avatar_UxrAvatar">UxrAvatar</a> has any Animator components, UltimateXR animation or hand poses will prevail.</td></tr></table>

## See Also


#### Reference
<a href="N_UltimateXR_Core">UltimateXR.Core Namespace</a><br />