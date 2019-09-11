---
吴芊瑶已完成mapbox-framer-x.md文件翻译
@Yuyan-lv
---
title: Prototype apps with Mapbox in Framer X
description: Learn how to use the Mapbox component to add a map to a prototype in Framer X.
thumbnail: framerXMapboxComponents
topics:
- third party integration
level: 1
language:
- No code
prereq: Familiarity with Framer X.
prependJs:
  - "import AppropriateImage from '../../components/appropriate-image';"
  - "import * as constants from '../../constants';"
contentType: tutorial
---

Mapbox为使用[Framer X](https://framer.com/)的组件允许设计者在无需编写代码的条件下完成基于位置的产品和应用程序的原型。在这个指南中，您将学习如何使用Mapbox的组件在Framer X的原型中添加功能多样、数据丰富的地图。原型由三种框架组成，每一种采用不同的制图方式。这个原型能够模拟一个允许用户搜索、使用动画展示搜索结果并用一系列图标标识的应用程序。


{{
<AppropriateImage imageId="framerXMapboxComponents" alt="Screenshot showing a prototype in Framer X that uses all three Mapbox components: Mapbox, SequentialLocationMap, and MarkerMap" />
}}

## 开始

这里有一些在开始之前您需要知道的信息：

- **一个Mapbox的账号和访问口令.** 在[mapbox.com/signup](https://www.mapbox.com/signup/) 注册一个Mapbox账号。您的访问口令在您的[账户界面](https://www.mapbox.com/account).
- **一个Frame的账号.** 您需要在您的电脑中安装[Framer X](https://framer.com/)。您需要比较熟悉如何使用Frame X。

## 下载Mapbox组件

这部分假设您具有一定使用FramerX的经验。如果您在使用Framer X的时候需要帮助，请查阅[Framer的文档](https://framer.com/docs/)。

1. 在Framer X中点击**Store**图标。
1. 在搜索栏中搜索`Mapbox`。
1. 选择Mapbox组件并点击**Install**.

## 使用Mapbox组件
在第一种框架中，您将使用**Mapbox**组件制作一个具有丰富搜索功能的地图。

1. 在Mapbox组件安装完成之后，点击**Tools**图标。
1. 点击**Frame**按钮（或者按`F`键）向您的工程中添加一个框架。这个指南中的样例使用了苹果iPhone 8的预置尺寸。您可以从右侧的下拉菜单中选择您喜欢的任意预置框架尺寸，或者您可以点击并通过拖拽创建自定义尺寸的框架。
1. 点击**Components**图标。这里有一些组件可供选择： **`Mapbox`**， **`SequentialLocationMap`** 和 **`MarkerMap`**。
1. 点击`Mapbox`组件并将它拖入框架中。
1. 框架中将被一个新的Mapbox地图所填充。您可以调整地图在框架中的大小和位置。

{{
<AppropriateImage imageId="framerXAddMapboxComponent" alt="Screenshot showing how to add the Mapbox component to a Framer X prototype" class="mx-auto block" />
}}

### 添加您的Mapbox访问口令
Mapbox组件在默认情况下站是一个功能丰富的地图，但它会在地图的左下角显示一个写着“获取您的访问口令”的文本水印。当您添加了您的Mapbox访问口令，这个文本水印就会消失。

1. 导航到您的[Mapbox账户界面](https://account.mapbox.com/)。点击在复制您的 _default public token_ 旁边的**clipboard icon**来复制访问口令。
1. 在Framer X中，将访问口令粘贴到 _access token_ 区域。点击回车键将它应用到当前框架中。

之后，您可以将地图样式更改为地图设计器样式。

{{
<AppropriateImage imageId="framerXAddAccessToken" alt="Screenshot showing how to add a Mapbox access token to Framer X" class="mx-auto block" />
}}

### 更改地图样式

Mapbox组件默认为您提供一些Mapbox的核心样式（Mapbox Light，Mapbox Dark，Mapbox Streets，Mapbox Satellite和Mapbox Satellite Streets），即使您没有添加访问口令，您也可以使用这些样式。但是如上一节所述，如果您想要使用任意Mapbox设计器样式或者创建自定义地图样式，您需要使用您的Mapbox访问口令。

更改地图设计：

1. 在Framer X中，点击**Map style**下拉菜单。
1. 点击**LeShine**样式。

Mapbox组件中的地图将更新为使用LeShine的Mapbox设计器样式。

{{
<AppropriateImage imageId="framerXChangeMapStyle" alt="Screenshot showing where to change the map style in Framer X" class="mx-auto block" />
}}

### 更新地图位置

Mapbox组件为您在原型中的使用设置一系列默认地点。您也可以选择添加自定义位置。

1. 点击**City**下拉菜单。
1. 点击"Washington DC, USA"。

地图中显示的位置将更换到Washington DC。

{{
<AppropriateImage imageId="framerXChangeLocation" alt="Screenshot showing where to change the city view in Framer X" class="mx-auto block" />
}}

### 添加搜索栏

之后，您将添加功能丰富的Mapbox搜索栏到这个框架中。

1. 点击 _Search_ 选项旁边的**Show**按钮。
1. 使用 _Position_ 下拉菜单将搜索栏移至地图的左上方。
1. 使用 _Offset_ 区域将搜索栏向下移动`15`像素。
1. _Drop Pin_ 选项默认为**True**。在这个样例中，如果您希望您原型中的搜索结果被图钉标识，请使用默认设置设置。

{{
<AppropriateImage imageId="framerXAddSearchBar" alt="Screenshot showing how to add a search bar to the Mapbox component in Framer X" class="mx-auto block" />
}}

要预览此框架，请点击Framer X界面右上方的**Preview**图标。在预览界面中，您可以在搜索栏中输入一个地点并选择一个结果。地图将切换到您选中的地点。

## 使用`SequentialLocationMap`组件

之后，您将新建一个使用 **`SequentialLocationMap`** 组件的新框架。在这个框架中，您将在建立能够展示高度、方向和缩放变化的搜索结果界面。

1. 点击**Frame**按钮（或者点击`F`键）向您的工程中添加另一个iPhone 8框架。
1. 点击**Components**图标并将`SequentialLocationMap`组件拖拽到新的框架中。
1. 将访问口令粘贴到 _access token_ 区域。点击回车键将它应用到当前框架中。
1. 点击**Map Style**下拉菜单并选择**LeShine**样式。

### 设置地图位置

1. 点击**Code**标签展开。
2. 点击 _File_ 旁边的下拉菜单并选择**New File**。（如果出现提示，请下载Visual Studio Code。）
3. Framer X将在Visual Studio Code中打开一个`.tsx`文件。删除文件中的内容并将以下代码粘贴进去： 
```js
import { Override } from "framer";

// To control what locations the map looks at, provide an
// array of location values. All properties for the locations are optional,
// with any unspecified values reverting to the current map's values.
// Valid properties are:
// latitude, longitude, zoom, bearing, pitch
export const CameraMoveSequence: Override = () => {
  return {
    locations: [
      // set the location to Sydney, Australia
      { bearing: 0, pitch: 0, zoom: 11, latitude: -33.86729979946806, longitude: 151.209683984967 },
      // zoom in to the location
      { zoom: 13 },
      // change the pitch of the map
      { pitch: 60 },
      // change the bearing of the map
      { bearing: 90 }
    ]
  };
};
```
4. 保存文件。您可以选择使用**Save As**重命名文件，但文件必须使用`.tsx`格式。
5. 在Framer X中，点击 _File_ 旁边的下拉菜单并选择您新建的文件。
6. 点击 _Overrid_ 旁边的下拉菜单并选择 **`CameraMoveSequence`** 。
7. 将 _Autoplay_ 区域的值设为**True**。这将在预览模式下自动启动动画。

{{
<AppropriateImage imageId="framerXSetSequentialLocation" alt="Screenshot showing the how to set the locations for the SequentialLocationMap component in Framer X" class="mx-auto block" />
}}

要预览此框架，请点击Framer X界面右上方的**Preview**图标。预览将显示悉尼并将浏览您在`.tsx`文件中设置的动画。

## 使用`MarkerMap`组件

之后，您将新建一个使用 **`MarkerMap`** 组件的新框架。在这个框架中，您将对显示多个标记位置的地图进行原型设计。

1. 点击**Frame**按钮（或者点击`F`键）向您的工程中添加另一个iPhone 8框架。
1. 点击**Components**图标并将`MarkerMap`组件拖拽到新的框架中。
1. 将访问口令粘贴到 _access token_ 区域。点击回车键将它应用到当前框架中。
1. 点击**Map Style**下拉菜单并选择**LeShine**样式。

### 设置标记位置

`MarkerMap`组件需要一个具有有效GeoJSON格式的文件来设置标记位置。

1. 打开Visual Studio Code或您选择的文本编辑器。
1. 新建一个文件并命名为`sydney_attractions.json`。
1. 将以下代码复制到新文件中：
```js
[
  {
    "name": "Sydney Opera House",
    "location": { "longitude": 151.21507755097377, "latitude": -33.85725554523418 },
    "focusLocation": { "zoom": 9 },
    "category": "cultural attraction",
    "details": "World-famous opera house designed by Jørn Utzon. Opened in 1973."
  },
  {
    "name": "Bondi Beach",
    "location": { "longitude": 151.27362005956923, "latitude": -33.89084702828488 },
    "focusLocation": { },
    "category": "beach",
    "details": "A popular beach located in a Sydney suburb of the same name."
  },
  {
    "name": "Darling Harbour",
    "location": { "longitude": 151.20180875882124, "latitude": -33.87151653767559 },
    "focusLocation": { },
    "category": "cultural attraction",
    "details": "A large recreational and pedestrian precinct situated on the west side of the Sydney central business district."
  },
  {
    "name": "Sydney Harbour Bridge",
    "location": { "longitude": 151.21064244901527, "latitude": -33.8522736348907 },
    "focusLocation": { },
    "category": "cultural attraction",
    "details": "Distinctive bridge between the Sydney central business district and the North Shore. Opened in 1932. "
  },
  {
    "name": "Royal Botanical Gardens",
    "location": { "longitude": 151.21602755096444, "latitude": -33.86416527202888 },
    "focusLocation": { },
    "category": "cultural attraction",
    "details": "The oldest botanical garden in Australia. Opened in 1816."
  }
]
```
4. 在Framer X中，点击 _Location_ 选项旁边的**Choose File**按钮。选择`sydney_attractions.json`文件。
5. 将经度`151.2356`粘贴到 _Longitude_ 区域。
6. 将纬度`-33.8682`粘贴到 _Latitude_ 区域。
7. 将 _Zoom_ 的值调整为`11`。
8. 点击 _Search_ 选项旁边的**Show**按钮。
9. 使用 _Position_ 下拉菜单将搜索栏移至地图的左上方。
10. 使用 _Offset_ 区域将搜索栏向下移动`15`像素。

{{
<AppropriateImage imageId="framerXUpdateMarkerMapComponent" alt="Screenshot showing the how to set up the MarkerMap component in Framer X" class="mx-auto block" />
}}

要预览此框架，请单击Framer X屏幕右上角的**Preview**图标。预览将显示Sydney以及在`sydney_attractions.json`中描述的每个地点的标记。如果在预览模式下单击标记，它将显示具体信息，其中包含来自`.json`文件的`name`，`category`和`details`的属性信息。

{{
<AppropriateImage imageId="framerXPreviewMarkerMapComponent" alt="Screenshot showing a preview of the MarkerMap component in Framer X" class="mx-auto block" />
}}

## 框架关联

最后，您将关联三个框架以创建一个原型。

1. 点击第一个框架，您将看到紫色的框架边框显示它被选中。
1. 点击框架右侧的紫色圆形并拖拽它，将第一个和第二个框架关联。
1. 要关联第二个和第三个框架，您需要在第二个框架中新建一个按钮。点击**Frame**按钮（或者点击`F`键）向第二个框架上添加一个新的框架。您可以通过屏幕右侧的控制栏选择调整新按钮的位置、尺寸、颜色和透明度。您也可以为按钮添加文字，比如“Show me places to visit!”。
1. 选择按钮并按`L`键建立连接线。拖动连接线关联到第三个框架。

{{
<AppropriateImage imageId="framerXConnectFrames" alt="Screenshot showing the connected frames in Framer X" />
}}

## 产品完成

您已经使用Mapbox为使用Frame X的组件创建了一个原型。当您点击预览按钮，您可以看到您的新搜索应用程序的原型。将“Sydney”键入搜索框，并选择“Sydney, New South Wales, Australia”选项。原型将会展示Sydney并并浏览您在`SequentialLocationMap`组件中设置的动画。然后点击按钮，该按钮将显示您在`MarkerMap`组件中设置的地图位置的标记。

{{
<AppropriateImage imageId="framerXMapboxComponents" alt="Screenshot showing a prototype in Framer X that uses all three Mapbox components: Mapbox, SequentialLocationMap, and MarkerMap" />
}}

## Next steps
- 要获取更多如何使用Mapbox为Framer X的提示，请观看我们的教程视频[`Mapbox`组件](https://www.mapbox.com/videos/how-to/install-and-use-mapbox-component-in-framer-x/), the [`SequentialLocationMap`组件](https://www.mapbox.com/videos/how-to/install-and-use-sequentiallocationmap-component-in-framer-x/), and the [`MarkerMap`组件](https://www.mapbox.com/videos/how-to/install-and-use-markermap-component-in-framer-x/).
- 要获取关于如何创建能够在Farmer X中使用的自定义地图样式，请阅读[Mapbox Studio Manual](https://www.mapbox.com/studio-manual/overview/)。您也可以浏览Mapbox[style gallery](https://www.mapbox.com/designer-maps/)来获取想法！
- 想继续关注Mapbox为Framer X的组件的进展？请注册[Framer X component page](https://mapbox.com/framerx).
