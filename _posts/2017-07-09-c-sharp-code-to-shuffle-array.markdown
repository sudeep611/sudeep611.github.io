---
layout: post
title:  "C# code to shuffle Array"
categories: Programming
tags: CSharp
---
```csharp
private T[] ShuffleArray<T>(T[] array) {
    System.Random r = new System.Random ();
    for(int i = array.Length; i > 0; i--) {
        int j = r.Next (i);
        T k = array [j];
        array [j] = array [i - 1];
        array [i - 1] = k;
    }

    return array;
}
```

Example:

<h2>Int Array</h2>
```csharp
int[] intArray = new int[] {1,2,3,4};

intArray = ShuffleArray(intArray);
```

<h2>Float Array</h2>
```csharp
float[] floatArray = new float[] {1.0f,2.0f,3.0f,4.0f};

floatArray = ShuffleArray(floatArray);
```
