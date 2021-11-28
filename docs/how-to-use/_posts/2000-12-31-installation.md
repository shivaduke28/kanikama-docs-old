---
layout: default
---

# Installation

## 1. Import Unity Packages

Import Unity Packages into your Unity project in the following order:

1. [VRC SDK3](https://vrchat.com/home/download)
2. [MerlinVR/UdonSharp](https://github.com/MerlinVR/UdonSharp)
3. [KanikamaGI](https://github.com/shivaduke28/kanikama/releases)

## 2. Project Settings

```
Edit > Project Settings > Player > Other Settings > Rendering
```
- **Color Space**: should be Linear
- **Lightmap Encoding**: should be High Quality


## 3. Lighting Settings

```
Window > Rendering > Light Settings
```

- **Realtime Global Illumination**: should be unchecked
- **Baked Global Illumination**: should be checked
- **Lightmapper**
  - Progressive CPU: It is highly accurate, but it takes time.
  - Progressive GPU: It is fast than CPU, but can produce many artifacts on lightmaps. It is convenient to use GPU during the development stage and bake on the CPU before publishing.
  - Enlighten: It can be used.