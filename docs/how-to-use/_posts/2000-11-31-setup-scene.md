---
layout: default
---

# Setup Scene

## KanikamaSceneDescriptor

Put **KanikamaSceneDescriptor** object in your scene.
You can find a Prefab in the following path:

`Assets/Kanikama/prefabs/KanikamaSceneDescriptor.prefab`

KanikamaSceneDescriptor object has the following fields:

- Kanikama Lights
- Kanikama Renderers
- Kanikama Light Source Groups

### Kanikama Lights

If you have Light objects whose effect you want to change on GI at runtime, specify them in this field using the following components:

- KanikamaUnityLight
- KanikamaBakeryDirectLight
- KanikamaBakeryPointLight
- KanikamaBakeryLightMesh (with Area Light)

If you want to update the scene's Ambient Light, use the following components:

- KanikamaUnitySkyLight
- KanikamaBakerySkyLight

Due to Kanikama's implementation, these objects require Unity's Light component, which can be disabled and used only to specify **Color** and **Intensity** at runtime.

## Kanikama Renderers

If you have renderers with emissive materials whose effect you want to change on GI at runtime, specify them in this field using the following components:

- KanikamaUnityRenderer
- KanikamaBakeryLightMesh (with Renderer)

Emissive materials must satisfy:

- `_EMISSION` Shader keywor is defined.
- `_EmissionColor` property of `Color` type is defined.

When you use Unity's Standard shader (or Kanikama/Standard shader), materials need to be configured as:

- **Emission** is checked.
- **Emission Color** is brighter than black `(0,0,0,1)`.
- **Global Illumination** is **Baked**.

## Kanikama Light Source Groups

This field can be used to LightSourceGroup objects. A typical (and at the moment the only) example is a monitor that contributes to GI.