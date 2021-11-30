---
layout: default
---

# KanikamaMonitorQuad

The **KanikamaMonitorQuad** component can be used for a Kanikama Monitor with Quad mesh.
Any KanikamaMonitorController require this component as its Main Monitor.

Note that when KanikamaGI bakes lightmaps, the system make Renderers of KanikamaMonitors disabled so that they can not contribute GI at all.

[![Image from Gyazo](https://i.gyazo.com/e7cb2ca5fe1df9d1c2828b54c425b5c4.png)](https://gyazo.com/e7cb2ca5fe1df9d1c2828b54c425b5c4)


|Properties:|Function:|
|-|-|
|**Monitor Renderer**| The Renderer attached to its GameObject.|
|**rid Renderers**| A list of **KanikamaGridRenderers** that gives a split of the monitor. This field is automatically set by clicking **Setup** button of the Inspector window of the KanikamaMonitorController component.|
|**Advanced**||
|&nbsp;Is Grid Renderer Locked| If enabled, then the system will not update grid renderers.|
|&nbsp;Override Prefab| If not null, then it is used for this monitor's grid renderers. This is useful when you have multiple monitors and ther shapes/brightness are different.|
