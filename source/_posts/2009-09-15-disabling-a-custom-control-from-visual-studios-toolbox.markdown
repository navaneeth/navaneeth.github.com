---
layout: post
title: "Disabling a custom control from Visual Studio’s toolbox"
date: 2009-09-15 23:52
comments: true
categories: .net, c#, visual studio 
---

When a custom control is created, Visual Studio will show it in the toolbox for dragging and dropping. This can be annoying when you create a composite control which is a combination of several other custom controls where VS will display all custom controls in the toolbox. `System.ComponentModel.ToolBoxItemAttribute` can be used with the controls that you want to hide from toolbox. Apply this attribute to all the controls that you want to hide from toolbox.

Sample code

```csharp
[System.ComponentModel.ToolboxItem(false)]
public class MyCustomControl : Label
{
}
```

`MyCustomControl` will not be displayed on the toolbox.
