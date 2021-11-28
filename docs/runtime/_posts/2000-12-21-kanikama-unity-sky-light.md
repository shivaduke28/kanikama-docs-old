---
layout: default
---

# KanikamaUnitySkyLight

Use the **KanikamaUnitySkyLight** component when you want to update the Ambient Light's effect to lightmaps at runtime.
Add this component to such a Light object and then register it in “Kanikama Lights” field of the KanikamaSceneDesciptor component.

This component requires Light component that **usually should be disabled**.

The light object is not used on baking.\\
At runtime, the light object's **color** and **intensity** fields are used to hold the current color of the ambient light.
You can change these fields by custom Udon scripts and Animations.

![image](https://user-images.githubusercontent.com/45098240/143771606-a1d12404-2a1d-4f53-a2f1-0b6304898856.png)

