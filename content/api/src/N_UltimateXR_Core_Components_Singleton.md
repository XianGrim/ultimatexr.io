# UltimateXR.Core.Components.Singleton Namespace

## Classes
&nbsp;<table><tr><th></th><th>Class</th><th>Description</th></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="T_UltimateXR_Core_Components_Singleton_UxrAbstractSingleton_1">UxrAbstractSingleton(T)</a></td><td>

A singleton base class that can be used with abstract classes.

The difference with <a href="T_UltimateXR_Core_Components_Singleton_UxrSingleton_1">UxrSingleton(T)</a> is that <a href="T_UltimateXR_Core_Components_Singleton_UxrSingleton_1">UxrSingleton(T)</a> guarantees that an instance will always be available in the scene by instantiating the component if it's not found. This means <a href="P_UltimateXR_Core_Components_Singleton_UxrSingleton_1_Instance">Instance</a> will always be non-null and can be used with or without an instance available in the scene. <a href="T_UltimateXR_Core_Components_Singleton_UxrSingleton_1">UxrSingleton(T)</a> also allows to use automatic prefab instantiation if a compatible singleton prefab is present in a special Resources folder. Since abstract classes can't be instantiated, <a href="P_UltimateXR_Core_Components_Singleton_UxrAbstractSingleton_1_Instance">Instance</a> in <a href="T_UltimateXR_Core_Components_Singleton_UxrAbstractSingleton_1">UxrAbstractSingleton(T)</a> will be non-null only if a child component is available somewhere in the scene.

For design purposes, a singleton may still be desirable when programming an abstract class, hence this <a href="T_UltimateXR_Core_Components_Singleton_UxrAbstractSingleton_1">UxrAbstractSingleton(T)</a> component base class.</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="T_UltimateXR_Core_Components_Singleton_UxrAsyncInitAbstractSingleton_1">UxrAsyncInitAbstractSingleton(T)</a></td><td>
Same as <a href="T_UltimateXR_Core_Components_Singleton_UxrAsyncInitSingleton_1">UxrAsyncInitSingleton(T)</a> but allows asynchronous initialization. This can be useful where singletons require initialization through config files that are loaded asynchronously from disk or through network.</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="T_UltimateXR_Core_Components_Singleton_UxrAsyncInitSingleton_1">UxrAsyncInitSingleton(T)</a></td><td>
Same as <a href="T_UltimateXR_Core_Components_Singleton_UxrSingleton_1">UxrSingleton(T)</a> but allows asynchronous initialization. This can be useful where singletons require initialization through config files that are loaded asynchronously from disk or through network.</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="T_UltimateXR_Core_Components_Singleton_UxrSingleton_1">UxrSingleton(T)</a></td><td>

An improved singleton implementation over <a href="T_UltimateXR_Core_Components_Singleton_UxrAbstractSingleton_1">UxrAbstractSingleton(T)</a> for non-abstract classes. <a href="T_UltimateXR_Core_Components_Singleton_UxrSingleton_1">UxrSingleton(T)</a> guarantees that an <a href="P_UltimateXR_Core_Components_Singleton_UxrSingleton_1_Instance">Instance</a> will always be available by instantiating the singleton if it wasn't found in the scene. Additionally, it can instantiate a prefab if there is one available in a well-known location.

The steps followed by this singleton implementation to assign the instance are the:
&nbsp;<ol><li>The singleton component is searched in the scene to see if it was pre-instantiated or is already available.</li><li>If not found, the component tries to be instantiated in the scene using a prefab in a well known Resources folder. The well known path is <a href="F_UltimateXR_Core_UxrConstants_Paths_SingletonResources">SingletonResources</a> in any Resources folder and the prefab name is the singleton class name. A prefab allows to assign initial properties to the component and also hang additional resources (meshes, textures) from the GameObject if needed.</li><li>If not found, a new GameObject is instantiated and the singleton is added using AddComponent``1().</li></ol></td></tr></table>&nbsp;