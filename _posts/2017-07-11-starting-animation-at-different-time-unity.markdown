---
layout: post
title:  "Starting Animation from random time frame Unity"
categories: Programming
tags: CSharp, Unity3D
---
Code snippet to start the animation at different time. Useful when there are many same animation running on screen and you want to make them random.

```csharp
Animator anim = GetComponent<Animator> ();
AnimatorStateInfo state = anim.GetCurrentAnimatorStateInfo (0);
anim.Play (state.fullPathHash, -1, Random.Range(0f,1f));
```

You can add this code in Start or Awake function and add to the GameObject with the Animator component.
