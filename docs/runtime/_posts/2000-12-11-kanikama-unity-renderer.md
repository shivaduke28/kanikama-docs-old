---
layout: default
---

# KanikamaUnityRenderer

KanikamaGI uses the **KanikamaUnityRenderer** component to specify Renderer objects with emissive materials that contribute lightmaps and are going to be updated at runtime.

## Emissive materials
Emissive materials must satisfy:

- `_EMISSION` Shader keywor is defined.
- `_EmissionColor` property of `Color` type is defined.

When you use Unity's Standard shader (or Kanikama/Standard shader), materials need to be configured as:

- **Emission** is checked.
- **Emission Color** is brighter than black `(0,0,0,1)`.
- **Global Illumination** is **Baked**.

![image](https://user-images.githubusercontent.com/45098240/143772079-d7d4648b-8c83-4443-b7c7-bc1df27643cc.png)

## Setup

Add this component to such a Renderer object and click **Setup Materials** button in the Inspector.
If materials are configured correctly, **Light Materials** field is setuped automatically.

Then register it in the **Kanikama Renderers** field of the KanikamaSceneDesciptor component.

![image](https://user-images.githubusercontent.com/45098240/143772215-21361085-38fa-46a5-ad9a-f98dc0b5df94.png)

