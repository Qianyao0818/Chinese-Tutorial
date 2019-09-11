吴芊瑶已完成mapbox-with-openlayers.md文件翻译
@Yuyan-lv
---
title: Use Mapbox with OpenLayers
description: Learn how to use Mapbox with OpenLayers.
thumbnail: openLayersThumb
level: 2
topics:
- third party integration
language:
- JavaScript
prereq: Familiarity with front-end development concepts.
prependJs:
  - "import * as constants from '../../constants';"
  - "import UserAccessToken from '../../components/user-access-token';"
  - "import Note from '@mapbox/dr-ui/note';"
  - "import DemoIframe from '@mapbox/dr-ui/demo-iframe';"
contentType: tutorial
---

您可以在[OpenLayers](http://openlayers.org/two/)中使用[Mapbox](https://www.mapbox.com/developers/api/) 的样式。从选择您使用的OpenLayers的版本和Mapbox的工具开始。

{{
  <DemoIframe gl={false} src="/help/demos/openlayers/openlayers3.html" />
}}

## 开始

这里有一些在您开始在OpenLayers中使用Mapbox前需要了解的内容：

- **您的Mapbox访问口令**。您可以在您的Mapbox[账户页面](https://www.mapbox.com/account/) 找到您的Mapbox访问口令。
- **样式URL**。您可以在您的Mapbox账户[style](https://www.mapbox.com/studio/styles/) 页面找到[style URL](/help/glossary/style-url/) 。

## OpenLayers 3.x

您可以在[OpenLayers 3.x](http://openlayers.org/)加载[Mapbox Studio style or Mapbox style URL](#mapbox-studio-style-or-mapbox-style-url)或者[Mapbox tileset ID](#mapbox-tileset-id) 。

{{
  <DemoIframe gl={false} src="/help/demos/openlayers/openlayers3.html" />
}}

### Mapbox Studio样式或Mapbox样式URL

在OpenLayers 3.x中使用[Mapbox Studio style](https://www.mapbox.com/studio/styles/) 或[Mapbox style URL](/help/glossary/style-url/) ，您需要参考[Mapbox Static Tiles API](https://docs.mapbox.com/api/maps/#static-tiles)。您可以将style URL `mapbox/streets-v{{constants.VERSION_STREETS_STYLE}}`替换为您自己的。

```js
var map = new ol.Map({
  layers: [
    new ol.layer.Tile({
      source: new ol.source.XYZ({
        url: 'https://api.mapbox.com/styles/v1/mapbox/streets-v{{constants.VERSION_STREETS_STYLE}}/tiles/256/{z}/{x}/{y}?access_token={{ <UserAccessToken /> }}'
      })
    })
  ],
  target: 'map',
  view: new ol.View({
    center: [0, 0],
    zoom: 2
  })
});
```

### Mapbox tileset ID

在OpenLayers 3.x中使用[Mapbox tileset ID](/help/glossary/tileset-id/) ，您需要参考[Mapbox Raster Tiles API](https://docs.mapbox.com/api/maps/#raster-tiles)。您可以将tileset ID `mapbox.satellite`替换为您自己的。

```js
var map = new ol.Map({
  layers: [
    new ol.layer.Tile({
      source: new ol.source.XYZ({
        url: 'https://api.mapbox.com/v4/mapbox.satellite/{z}/{x}/{y}.png?access_token={{ <UserAccessToken /> }}'
      })
    })
  ],
  target: 'map',
  view: new ol.View({
    center: [0, 0],
    zoom: 2
  })
});
```

## OpenLayers 2.x

在OpenLayers 2.x中，请使用[OpenLayers.Layer.XYZ](http://dev.openlayers.org/docs/files/OpenLayers/Layer/XYZ-js.html)类。您可以在OpenLayers 2.x中加载[Mapbox Studio style or Mapbox style URL](#mapbox-studio-style-or-mapbox-style-url-1) 或者[Mapbox tileset ID](#mapbox-tileset-id-1)。

{{
  <DemoIframe gl={false} src="/help/demos/openlayers/openlayers2.html" />
}}

### Mapbox Studio样式或Mapbox样式URL

在OpenLayers 2.x中使用[Mapbox Studio style](https://www.mapbox.com/studio/styles/)或者[Mapbox style URL](/help/glossary/style-url/) ，您需要参考[Mapbox Static Tiles API](https://docs.mapbox.com/api/maps/#static-tiles)。您可以将style URL `mapbox/streets-v{{constants.VERSION_STREETS_STYLE}}`替换为您自己的。

```js
var myLayer = new OpenLayers.Layer.XYZ(
  'My Map Layer',
  ['https://api.mapbox.com/styles/v1/mapbox/streets-v{{constants.VERSION_STREETS_STYLE}}/tiles/256/${z}/${x}/${y}?access_token={{ <UserAccessToken /> }}'],
  {
    sphericalMercator: true,
    wrapDateLine: true
  }
);
var map = new OpenLayers.Map({
  div: 'map',
  layers: [myLayer],
  center: [0, 0],
  zoom: 1
});
```

### Mapbox tileset ID

在OpenLayers 2.x中使用[Mapbox tileset ID](/help/glossary/tileset-id/) with OpenLayers 2.x，您需要参考[Mapbox Raster Tiles API](https://docs.mapbox.com/api/maps/#raster-tiles)。您可以将`mapbox.satellite`替换为您自己的。


```js
var myLayer = new OpenLayers.Layer.XYZ(
  'My Map Layer',
  ['https://a.tiles.mapbox.com/v4/mapbox.satellite/${z}/${x}/${y}.png?access_token={{ <UserAccessToken /> }}'],
  {
    sphericalMercator: true,
    tileSize: new OpenLayers.Size([512, 512]),
    wrapDateLine: true
  }
);
var map = new OpenLayers.Map({
  div: 'map',
  layers: [myLayer],
  center: [0, 0],
  zoom: 1
});
```
