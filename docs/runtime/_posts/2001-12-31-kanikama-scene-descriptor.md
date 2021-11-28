---
layout: default
---

# KanikamaSceneDescriptor

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



## Kanikama Light Source Groups

This field can be used to LightSourceGroup objects. A typical (and at the moment the only) example is a monitor that contributes to GI.