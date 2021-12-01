---
layout: default
---

# Composition Mode

## Overview

KanikamaGI provides the following three composition methods for compositing lightmaps at runtime.


|Composition Mode|Provider|Asset|Kanikama Mode|Directional Mode|
|-|-|-|-|
|Receiver Shader|KanikamaMapArrayProvider|Texture2DArray|Array/Directional| ○ |
|CustomRenderTexture|KanikamaMapProvider|CustomRenderTexture|Single| × |
|RenderTexture with Camera|KanikamaMapProvider|RenderTexture|Single| × |


<br>

## Receiver Shaders

"Receiver" refers to static Renderers that are affected by KanikamaGI.

This mode uses the KanikamaMapArrayProvider component.
A provider distributes Tex2DArrays to receivers at the start of a Scene, and distributes "color coefficients" of lightmaps to the receivers in every frame.
Each receiver's shader uses the provided Tex2DArray and the color coefficients to compose its lightmap color for each pixel.

Features
- In VR, the compositing process may be performed for each of the left and right eyes.
- No frame delay in GI.
- Support Directional Mode.

If use the **Kanikama/Standard** shader for receivers,
specify its Kanikama Mode to Array in the material settings .


## CustomRenderTexture

This mode uses CustomRenderTextures to composite lightmaps and the KanikamaMapProvider component as "provider".
A KanikamaMapProvider distributes those CustomRenderTextures to receivers (as Textures) at the start of Scene, and set "color coefficients" of lightmaps to the materials of CustomRenderTextures.
Each receiver's shader just samples its provided CustomRenderTexture for each pixel.


Features
- Lightmap compositing is always performed for all texels in all lightmaps, regardless of whether the corresponding receivers are rendered or not.
- No matter how many times a point of a receiver is drawn in the same frame, the lightmap composition will only be performed once.
- When using a monitor, the reflection of the video on the GI is always delayed by one frame .
- Does not support Directional mode.

If use the **Kanikama/Standard** shader for receivers,
specify its Kanikama Mode to Single in the material settings .


## RenderTexture with Camera

In this mode, Cameras are used to compose lightmaps. Place a Quad or RawImage with the **Kanikama/Composite/Unlit** shader, and render it with a Camera. The result of the composite is output as a RenderTexture, which is distributed to the receiver in the same way as CustomRenderTexture mode.

Features
- You need to place Cameras and Quads, which is a pain to set up.
- Lightmap compositing is always performed for all texels in all lightmaps, regardless of whether the corresponding receivers are rendered or not.
- No matter how many times a point of a receiver is drawn in the same frame, the lightmap composition will only be performed once.
- No frame delay in GI.
- Does not support Directional mode.

If use the **Kanikama/Standard** shader for receivers,
specify its Kanikama Mode to Single in the material settings .
