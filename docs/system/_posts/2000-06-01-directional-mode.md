---
layout: default
---

# Directional Mode

Unity's Directional Mode can also be used for KanikamaGI.

[Unity - Manual: Directional Mode](https://docs.unity3d.com/2019.4/Documentation/Manual/LightmappingDirectional.html)

- When using Directional mode, KanikmaGI will be affected by the normal map.
- Directional maps are required in addition to the normal lightmap, which increases the size of the scene.
- Directional mode cannot be used in conjunction with compositing using RenderTexture or CustomRenderTexture.



Directional mode off

[![Image from Gyazo](https://i.gyazo.com/358c2be647cfd77c74da7867f6b0a6a5.png)](https://gyazo.com/358c2be647cfd77c74da7867f6b0a6a5)

Directional mode on

[![Image from Gyazo](https://i.gyazo.com/694d3d9f1914ed42c20bbe76c9e362a0.png)](https://gyazo.com/694d3d9f1914ed42c20bbe76c9e362a0)

## How to use

First, set the scene's Directional mode to On.

Open the Lighting Settings window from
```
Window > Rendering > Lighting Settings
```

and speficy `Lightmapping Settings > Directional Mode` to **Directional**.

[![Image from Gyazo](https://i.gyazo.com/19c29fa6689bc6d507a958ec702e11ad.png)](https://gyazo.com/19c29fa6689bc6d507a958ec702e11ad)


Next, in the Kanikama Bake window, check the Directional Mode checkbox and perform the bake.

[![Image from Gyazo](https://i.gyazo.com/19c808f173ad05b3cb542a5a869ed611.png)](https://gyazo.com/19c808f173ad05b3cb542a5a869ed611)


Then Texture2DArray of Directional maps are also generated.

[![Image from Gyazo](https://i.gyazo.com/8c80e8811ec5c6ea8521e135d18ee229.png)](https://gyazo.com/8c80e8811ec5c6ea8521e135d18ee229)


Speficy them in the Inspector window of a **KanikamaMapArrayProvider** by clicking the **Setup** button.

[![Image from Gyazo](https://i.gyazo.com/0a957f791069c5a72b72ad787900c6ad.png)](https://gyazo.com/0a957f791069c5a72b72ad787900c6ad)

In the material settings of receivers' materials, change KanikamaMode to `Directional` mode.

[![Image from Gyazo](https://i.gyazo.com/699665d4e171cb6d3a98095ef5d9a625.png)](https://gyazo.com/699665d4e171cb6d3a98095ef5d9a625)

## Directional Specular

Check **Directional Specular** in the material settings.

[![Image from Gyazo](https://i.gyazo.com/756cf192a7cff8bb6600fe5b6eafded5.png)](https://gyazo.com/756cf192a7cff8bb6600fe5b6eafded5)
