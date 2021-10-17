---
layout: default
permalink: ''
---

# About

In Unity, [Realtime Global Illumination (Realtime GI)](https://docs.unity3d.com/2019.4/Documentation/Manual/realtime-gi-using-enlighten.html) using Enlighten is a powerful system for dynamically updating the GI. Although Unity has deprecated Realtime GI, it is still available and is the only officially supported way to update the GI at runtime.

Realtime GI is supported in VRChat ([1, 2]), but there are some situations when we want to update the GI without using RealtimeGI, for example to avoid its CPU load, and several users have developed methods to switch or update lightmaps by custom shaders and Udon scripts manually ([3,4,5]).

KanikamaGI is an OSS that implements such a "DIY" RealtimeGI. The method used here is not new and widely known, but it is designed to be available in as general situations as possible.

### Sample World

- [KanikamaGI — Created by: shivaduke｜VRChat](https://vrchat.com/home/launch?worldId=wrld_ebb1341f-15b5-4ca6-9f38-575dfb01bf01)


### Environment

- Unity2019.4.29f1
- VRChat SDK3
- [MerlinVR/UdonSharp](https://github.com/MerlinVR/UdonSharp)


### Features

- Powered by UdonSharp and works in VRChat.
- Can update every frame accurately.
- Can be used with regular static lightmaps.
- Includes a variant of Stanard shader with Kanikama functionality.
- Supports [Directional Mode](https://docs.unity3d.com/2019.4/Documentation/Manual/LightmappingDirectional.html).


### Supported light sources

- Light components (Baked and Mixed)
- Renderers with Emissive materials
- Ambient Light
- Monitors / Screens

### Comparison with RealtimeGI

Advantages
- There is no frame delay in updating the GI.
- Less CPU load.

Disadvantages
- The position and angle of the light sources in the scene cannot be changed.
- Generates as many light maps as there are light sources, which increases Scene capacity and VRAM load.
- Does not support light probes.


### When should I use it?

When there are a lot of flickering of light sources, such as screen showing VJ's image in club worlds, RealtimeGI will not be able to update the GI without delay.
Also, if your world is going to have a lot of players and you can't handle the CPU load of RealtimeGI, then KanikamaGI may be an option.

Notice that it will increase the number of textures and the cost of drawing the static objects that GI will reflect.



## References

- [1] [Lightroom Dynamic GI - Created by: Μerlin｜VRChat](https://vrchat.com/home/launch?worldId=wrld_dffadff5-a446-4d0f-9053-34ad7a9186a2)
- [2] [VRChatのワールドでRealTimeGIを扱う｜落雷｜pixivFANBOX](https://rakurai5.fanbox.cc/posts/1919059)
- [3] [ProjectCiAN 制作記｜wata_pj｜note](https://note.com/wata_pj/n/n612f66466313)
- [4] [カスタムGI　メモ｜wata_pj｜note](https://note.com/wata_pj/n/n3a6604f9189e)
- [5] [無　解説 - Imaginantia](https://phi16.hatenablog.com/entry/2021/05/29/204643)
