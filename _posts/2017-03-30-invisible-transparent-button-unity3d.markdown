---
layout: post
title:  "Invisible Transparent Button in Unity3D"
categories: Programming
tags: Unity3D
---
Today i was working on a project where i required to add the invisible button. I tried different methods like making button transparent, adding the image in the button. But then i came to know about this solution. I think that this is probably the best solution.

<h2>Steps to add invisible button in Unity3D</h2>

<strong>1. </strong>Add the Button. (UI -&gt; Button)<br/>
<strong>2. </strong>Edit the height and width of the button according to your fit.<br/>
<strong>3. </strong>Delete the Image(Script) and the text from the button.<br />
<strong>4. </strong>Create new C# script (Touchable.cs) and add the following code into it:


```csharp
// Touchable.cs
using UnityEngine;
using UnityEngine.UI;
#if UNITY_EDITOR
using UnityEditor;
[CustomEditor(typeof(Touchable))]
public class Touchable_Editor : Editor
{ public override void OnInspectorGUI(){} }
#endif
public class Touchable:Text
{ protected override void Awake() { base.Awake();} }
```

<strong>5. </strong>Add Touchable.cs script to the button.

Done!

Now you have the invisible button.

Source: <a href="http://answers.unity3d.com/questions/801928/46-ui-making-a-button-transparent.html">UnityForum</a>
