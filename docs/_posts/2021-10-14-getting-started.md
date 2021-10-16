---
layout: default
title: Getting Started
---

# Getting Started


## 1. Import UnityPackages

Import the following UnityPackage into your Unity project.

1. [VRC SDK3](https://vrchat.com/home/download)
2. [UdonSharp](https://github.com/MerlinVR/UdonSharp)
3. [KanikamaGI](https://github.com/shivaduke28/kanikama/releases)


## 2. Project Settings

{% highlight ruby linenos %}
def foo
  puts 'foo'
end
{% endhighlight %}


`Edit > Project Settings > Player > Other Settings > Rendering`

の欄で以下の設定を確認してください。

- Color Space: Linearにしてください。
- Lightmap Encoding: High Qualityにしてください。(Middle Qualityだと現在動作しません。対応したい。）


![colorspace](https://user-images.githubusercontent.com/45098240/129404118-7418bb46-da80-4933-ba06-fd38e18af6b0.png)

## 3.Lighting Settings

```
Window > Rendering > Light Settings
```
からLighting Settingsウィンドウを表示します。

- Realtime Lighting: Realtime Global Illuminationのチェックを外します。（共存できるかも。要検証）
- Mixed Lighting: Baked Global Illuminationの項目にチェックを入れます。Lighting Modeはどれでもいいはず（多分）。
- Lightmapping Settings: Lightmapperを以下の目的に応じて選択します。

| ライトマッパー | 説明 |
|----|----|
| Progressive CPU | 精度が高いですが、時間がかかります。|
| Progressive GPU |  速いですがCPUよりも質が低いらしいです。動作確認時にはこちらを使うことで開発がスムーズに進みます。|
| Enlighten | Progressive CPUと同様に精度が高いですが、時間がかかります。|

その他細かいパラメータなどはいい感じに設定してください。

![lightingsettings](https://user-images.githubusercontent.com/45098240/129404368-735d2c77-98b6-45ed-bd02-6afbfe8bd806.png)
