---
title: "An Introduction to Blender's Shaders"
published: false
category: blender
tags:
- shaders
---

A crucial part of the Blender pipeline is using shaders.
They are the main thing which defines how an object looks.
Understanding how they work and how to build your own shaders will put you on the path towards making better renders.

## Understanding Materials

When you create a new material, you are creating a new shader.
This shader uses the generic Principled BSDF shader, which is essentially an all-purpose shader.

### But what is a shader?

At its core, a shader is a piece of code that explains how an object should be rendered.
This code is written in special shader languages such as [GLSL](https://en.wikipedia.org/wiki/OpenGL_Shading_Language) or [HLSL](https://en.wikipedia.org/wiki/High-Level_Shading_Language).
Luckily though, as a Blender user you won't need to know these languages.

A shader recieves a bunch of information from the render engine, such as the current vertex, lighting information, etc.
It then takes this information, runs some calculations, and returns a few values.
These values can include displacement, normals, emission, etc.

Typically, a shader is run on each vertex on an object.
This means that the object is split up into a bunch of fairly small units and for each of those units, the shader is run.
