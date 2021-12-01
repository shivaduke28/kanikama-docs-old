---
layout: default
---

# Hello Kanikama

## Create a new Scene

- Create a new Scene and save it.
- Destroy the Directional Light object generated automatically.
- Create a Plane by `Create > 3D Object > Plane` and make it **Static**.


## Setup LightSources

- Create a Point Light by `Light > Point Light` and change it to **Baked** mode.
- Add **KanikamaUnityLight** component to the Light object.
- Repeat the above to create another Light (the position should be different from the first one).

<img src="https://i.gyazo.com/cbe5c31c9c60c40b4e361fec095f7080.png" width=400>

## KanikamaSceneDescriptor

- Drag `Assets/Kanikama/Prefabs/KanikamaSceneDescriptor.prefab` to the Scene and unpack the Prefab completely.
- Add two Lights created above to the **Kanikama Lights** property in the Inspector window of the KanikamaSceneDescriptor.

<img src="https://i.gyazo.com/95a003bf23153c49325c69f845425946.png" width=400>

## Kanikama Bake Window

- Open the **Kanikama Bake Window** from `Window > Kanikama > Bake`.
- Click the **Load/Create Settings Asset** button. A KanikamaSettings.asset will be created in `[YourSceneFolder]/[SceneName]_Kanikama/` Folder. You can open that folder by clicking **Open Assets Directory** button in the bottom of the window.
- Uncheck **Directional Mode** if checked.
- Check **Bake All**.

<img src="https://i.gyazo.com/0d1871a1d40d838471fc18e2cd32afa9.png" width=400>

## Bake

Click the **Bake** button.


KanikamaGI bakes lightmaps three times.

<img src="https://i.gyazo.com/6906bb40ecbdeea80969746e1989ebe6.png" width=240><img src="https://i.gyazo.com/b3d4dd0ab9d513880812d21432dbbc26.png" width=240><img src="https://i.gyazo.com/afbcb192f225d9311f8cdd45d31d50a6.png" width=240>

Then combine first two lightmaps into **KanikamaTexArray_0.asset** in the Kanikama asset directory.
In tmp directory you can also see indivisual lightmaps that are not used at runtime.


In the Console window, you can check Logs of the baking process.
[![Image from Gyazo](https://i.gyazo.com/b3803d1044475bf941a29e4172c96792.png)](https://gyazo.com/b3803d1044475bf941a29e4172c96792)


## Setup Udon scripts

- Drag `Assets/Kanikama/Prefabs/KanikamaMapArrayProvider.prefab` to your Scene and unpack it completely.
- Click the **Setup by KanikamaSettings asset** button in the Inspector window of the **KanikamaMapArrayProvider**.
- Click the **Setup by KanikamaSceneDescriptor** button in the Inspector window of the **KanikamaColorCollector**.

[![Image from Gyazo](https://i.gyazo.com/4918435b180f6e75e473825ae8aedba5.png)](https://gyazo.com/4918435b180f6e75e473825ae8aedba5)

## Setup Receivers

- Create a new Material and change its shader to **Kanikama/Standard**.
- Change its **Kanikama Mode** to **Array**.
- Set this Material to the Renderer of the Plane.
- Add the Renderer to the **Receivers** property of the **KanikamaMapArrayProvider**.

[![Image from Gyazo](https://i.gyazo.com/e00f7c2788264cee889892fcb9630c97.png)](https://gyazo.com/e00f7c2788264cee889892fcb9630c97)


## Hello World

- Place **VRCWorld** in your Scene.
- Play Unity Editor with CyanEmu.
- Change the colors of two Lights from the Inspector window.


[![Image from Gyazo](https://i.gyazo.com/e7bc945df7e3ffb7121d2c229a7d059a.png)](https://gyazo.com/e7bc945df7e3ffb7121d2c229a7d059a)