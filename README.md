* This is a test case for a bug with unity ECS


The problem

In some cases when using the entity debugger an exception is thrown and the preview gets truncated

![Inspector](Inpector.png)

When tryint to see the entity content in the entity debugger the console gets filled with:

<pre>
InvalidCastException: Specified cast is not valid.
Unity.Properties.Reflection.ReflectedMemberProperty`2[TContainer,TValue].GetValue (TContainer& container) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/Reflection/Properties/ReflectedMemberProperty.cs:24)
Unity.Properties.PropertyVisitor.VisitProperty[TProperty,TContainer,TValue] (TProperty property, TContainer& container, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyVisitor.cs:54)
Unity.Properties.Reflection.ReflectedPropertyBag`1+PropertyProxy`2[TContainer,TProperty,TValue].Accept[TVisitor] (TContainer& container, TVisitor visitor, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/Reflection/ReflectedPropertyBag.cs:19)
Unity.Properties.Reflection.ReflectedPropertyBag`1[TContainer].Accept[TVisitor] (TContainer& container, TVisitor visitor, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/Reflection/ReflectedPropertyBag.cs:58)
Unity.Properties.PropertyContainer.Visit[TContainer,TVisitor] (TContainer& container, TVisitor visitor, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyContainerVisit.cs:29)
Unity.Properties.PropertyVisitor.TryVisitContainerWithAdapters[TProperty,TContainer,TValue] (TProperty property, TContainer& container, TValue& value, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyVisitor.cs:127)
Unity.Properties.PropertyVisitor.VisitProperty[TProperty,TContainer,TValue] (TProperty property, TContainer& container, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyVisitor.cs:57)
Unity.Properties.Reflection.ReflectedPropertyBag`1+PropertyProxy`2[TContainer,TProperty,TValue].Accept[TVisitor] (TContainer& container, TVisitor visitor, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/Reflection/ReflectedPropertyBag.cs:19)
Unity.Properties.Reflection.ReflectedPropertyBag`1[TContainer].Accept[TVisitor] (TContainer& container, TVisitor visitor, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/Reflection/ReflectedPropertyBag.cs:58)
Unity.Properties.PropertyContainer.Visit[TContainer,TVisitor] (TContainer& container, TVisitor visitor, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyContainerVisit.cs:29)
Unity.Properties.PropertyVisitor.TryVisitContainerWithAdapters[TProperty,TContainer,TValue] (TProperty property, TContainer& container, TValue& value, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyVisitor.cs:127)
Unity.Properties.PropertyVisitor.VisitProperty[TProperty,TContainer,TValue] (TProperty property, TContainer& container, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyVisitor.cs:57)
Unity.Properties.Reflection.ReflectedPropertyBag`1+PropertyProxy`2[TContainer,TProperty,TValue].Accept[TVisitor] (TContainer& container, TVisitor visitor, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/Reflection/ReflectedPropertyBag.cs:19)
Unity.Properties.Reflection.ReflectedPropertyBag`1[TContainer].Accept[TVisitor] (TContainer& container, TVisitor visitor, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/Reflection/ReflectedPropertyBag.cs:58)
Unity.Properties.PropertyContainer.Visit[TContainer,TVisitor] (TContainer& container, TVisitor visitor, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyContainerVisit.cs:29)
Unity.Properties.PropertyVisitor.TryVisitContainerWithAdapters[TProperty,TContainer,TValue] (TProperty property, TContainer& container, TValue& value, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyVisitor.cs:127)
Unity.Properties.PropertyVisitor.VisitProperty[TProperty,TContainer,TValue] (TProperty property, TContainer& container, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyVisitor.cs:57)
Unity.Properties.VisitCollectionElementCallback`1[TContainer].VisitProperty[TElementProperty,TElement] (TElementProperty property, TContainer& container, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyVisitor.cs:17)
Unity.Entities.EntityContainerPropertyBag+ComponentsProperty+GetComponentDataCallback`1[TCallback].Invoke[TComponent] () (at Library/PackageCache/com.unity.entities@0.1.1-preview/Unity.Entities.Properties/EntityContainer.cs:65)
Unity.Properties.PropertyBag`1[TContainer].Cast[TCallback] (TCallback& callback) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/IPropertyBag.cs:38)
Unity.Entities.EntityContainerPropertyBag+ComponentsProperty.GetPropertyAtIndex[TGetter] (Unity.Entities.EntityContainer& container, System.Int32 index, Unity.Properties.ChangeTracker& changeTracker, TGetter getter) (at Library/PackageCache/com.unity.entities@0.1.1-preview/Unity.Entities.Properties/EntityContainer.cs:227)
Unity.Properties.PropertyVisitor.TryVisitCollectionWithAdapters[TProperty,TContainer,TValue] (TProperty property, TContainer& container, TValue& value, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyVisitor.cs:159)
Unity.Properties.PropertyVisitor.VisitCollectionProperty[TProperty,TContainer,TValue] (TProperty property, TContainer& container, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyVisitor.cs:87)
Unity.Entities.EntityContainerPropertyBag.Accept[TVisitor] (Unity.Entities.EntityContainer& container, TVisitor visitor, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.entities@0.1.1-preview/Unity.Entities.Properties/EntityContainer.cs:265)
Unity.Properties.PropertyContainer.Visit[TContainer,TVisitor] (TContainer& container, TVisitor visitor, Unity.Properties.ChangeTracker& changeTracker) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyContainerVisit.cs:29)
Unity.Properties.PropertyContainer.Visit[TContainer,TVisitor] (TContainer& container, TVisitor visitor, Unity.Properties.IVersionStorage versionStorage) (at Library/PackageCache/com.unity.properties@0.6.2-preview/Runtime/Unity.Properties/PropertyContainerVisit.cs:15)
Unity.Entities.Editor.EntitySelectionProxyEditor.OnInspectorGUI () (at Library/PackageCache/com.unity.entities@0.1.1-preview/Unity.Entities.Editor/EntityInspector/EntitySelectionProxyEditor.cs:44)
UnityEditor.UIElements.InspectorElement+<CreateIMGUIInspectorFromEditor>c__AnonStorey1.<>m__0 () (at C:/buildslave/unity/build/Editor/Mono/Inspector/InspectorElement.cs:501)
UnityEngine.GUIUtility:ProcessEvent(Int32, IntPtr)

</pre>

How to reproduce:

Open the scene **Assets/Scenes/MainScene**

Open the **Entity Debugger**

Select the **Bullet** entity

The inspector will appear truncated, the console should show the exceptions