---
layout: default
---



## Camera

Usually you do not have to modify it directly.

|Field|Note|
|-|-|
|Clear Flags|Don't Clear by default. Modify this if necessary (e.g., when the monitor is transparent).|
|Culling Mask|Everything by default. It is sufficient to include only the layer of the monitor object.|
|Projection|Should be Orthographic|
|Clipping Plances|This is set by KanikamaMonitorController automatically.|
|Viewport Rect|Should be `(0,0,1,1)`|
|Depth|-2 by default and should be smaller than the depth of the Camera component attached to the KanikamaProvider object (-1 by default) and the Main Camera (0 by default)|
|Target Texture|Should be a RenderTexture of 256x256|
|HDR|Should be enabled|
