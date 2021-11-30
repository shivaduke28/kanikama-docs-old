---
layout: default
---

# How it works

## Grid

KanikamaGI does not reflect the monitor image directly to GI as Enlighten RealtimeGI does.
Instead, KanikamaGI approximates RealtimeGI by dividing the monitor into several blocks (e.g., 2x2 or 3x3) and treating each block as a single light source.

In the next image, the monitor is divided into 3x2 blocks.

[![Image from Gyazo](https://i.gyazo.com/7f4519232a64f27c6190dd413f5540b8.gif)](https://gyazo.com/7f4519232a64f27c6190dd413f5540b8) 


The average color of each block is calculated by capturing the monitor image through the Camera component and sampling it at its appropriate mipmap level.


From left to right: monitor image, sampled colors, composited light map

[![Image from Gyazo](https://i.gyazo.com/b05fed27fe246479c1dd9a8ed0c8a2b0.gif)](https://gyazo.com/b05fed27fe246479c1dd9a8ed0c8a2b0)


## Capturing

1. A camera placed in front of a monitor renders monitor.
2. The camera ouputs it to a RenderTexture of 256x256 pixels.
3. The event function **OnPostRender** of the Udon script **KanikamaCamera** attached to the Camera object is called.
4. The Udon script calls the **Texture2D.ReadPixels** method of a Texture asset of 32x32 pixels.
5. The Udon script call the **Texture2D.GetPixels** method of the texture and store colors.
6. The Udon script **KanikamaColorCollector** collects colors from the **KanikamaCamera** object.

<img src="https://i.gyazo.com/a5cc9c8b1a11238dd926f234dab2070b.png" width="800">
