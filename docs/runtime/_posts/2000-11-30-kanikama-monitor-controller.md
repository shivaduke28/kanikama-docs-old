---
layout: default
---

# KanikamaMonitorController

Prefab path: `Assets/Kanikama/Prefabs/KanikamaMonitorCamera.prefab`

The **KanikamaMonitorController** component is an example of **LightSourceGroup**. This allows a monitor image to be dynamically reflected in light maps.

[![Image from Gyazo](https://i.gyazo.com/f41cb014232fd8046eac53eb54112bca.png)](https://gyazo.com/f41cb014232fd8046eac53eb54112bca)

|Property:|Function:|
|-|-|
|Camera|Reference to the Camera attached the the same GameObject.|
|GridRendererPrefab|Specify a Prefab that will be used for blocks of grids.|
|Partition Type|Specify which grid layout will be used to split monitors|
|Main Monitor|A "main" KanikamaMonitorQuad.|
|Sub Monitors|A list of "sub" KanikamaMonitors, that is, monitors displaying the same image as the Main Monitor. Not only the KanikamaMonitorQuad class but also user's custom classes extending the KanikamaMonitor class can be specified here.|
|Camera Detailed Settings|The postion of the Camera relative to the Main Monitor and the Clipping Planes of the Camera.|
|Traversed Grids|A lisf ot KanikamaMonitorGrids controlled by the object. This is set automatically by clicking "Setup" button in the Inspector window.|


## Setup

Prefab path: `Assets/Kanikama/Prefabs/KanikamaMonitorCamera.prefab`

1. Place the Prefab in your scene.
2. Unpack the Prefab completely.
3. Specify a Main Monitor.
4. Select Partition Type (2x2 or 3x2 are recommended).
5. Click the "Setup Lights and Camera" button in the Inspector window.
6. Add it to the "Light Group Sources" property of a KanikamaSceneDescriptor.