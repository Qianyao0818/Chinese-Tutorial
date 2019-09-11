吴芊瑶已完成mapbox-arcgis-qgis.md文件翻译
@Yuyan-lv
---
title: Add Mapbox maps as layers in ArcGIS and QGIS with WMTS
description: Learn how to add Mapbox maps as layers in ArcGIS and QGIS with WMTS.
thumbnail: mapboxArcgisQgis
level: 2
topics:
- third party integration
language:
- No code
prereq: Familiarity with and access to ArcGIS.
prependJs:
  - "import Icon from '@mapbox/mr-ui/icon';"
  - "import UserAccessToken from '../../components/user-access-token';"
contentType: tutorial
---

Mapbox提供很多URLs和代码片段来帮助您添加您自定义的Mapbox地图到其他绘图工具中。这个指南将指导您如何将任意Mapbox地图以图层形式和WMTS格式添加到ArcMap 或QGIS中。

## 开始

开始之前，请确保您已经做好如下准备：

- **一个Mapbox账户**。如果您还没有的话，[注册一个Mapbox账户](https://www.mapbox.com/signup/)。
- 在您的电脑上安装好**ArcMap**或者**QGIS**。在开始这个教程之前，您需要在一定程度上熟悉您的制图软件接口
- **Mapbox样式**. 去往您的账户中查看一系列样式[Mapbox studio中的样式界面](https://www.mapbox.com/studio/styles/) 。

## 在ArcMap中添加Mapbox地图

ArcMap可以读取地图瓦片协议，您将使用它来添加Mapbox样式。首先，您要为将添加到ArcMap的样式构建WMTS端点。接下来，您要将此WMTS端点添加到ArcMap项目中。

### 构建WMTS端点

用于在ArcMap中添加地图的WMTS端点需要遵循以下格式：

```
https://api.mapbox.com/styles/v1/YOUR_USERNAME/YOUR_STYLE_ID/wmts?access_token={{ <UserAccessToken /> }}

```

您需要更改此URL中的三个部分：
1. **Mapbox用户名:** 将"YOUR_USERNAME"替换为您的Mapbox用户名，您可以在您的[Mapbox Studio主页](https://www.mapbox.com/studio)中找到。
1. **Map样式ID:** 将"YOUR_STYLE_ID"替换为您要添加到ArcMap中的样式ID。 找到样式ID的方法:
    - 在您的[Mapbox Studio主页](https://www.mapbox.com/studio/)，从您的系列样式中找到正确的样式。
    - 点击{{<Icon name="menu" inline={true} />}}**Menu**按钮。
    - 点击{{<Icon name="clipboard" inline={true} />}}图标复制样式URL，它看起来像`mapbox://styles/YOUR_USERNAME/YOUR_STYLE_ID`。样式ID是这个URL的最后一部分。
1. **Mapbox访问口令:** 添加您的Mapbox访问口令，您可以在您的[Mapbox账户界面](https://www.mapbox.com/account)找到。

当您使用用户名、样式ID和访问口令自定义WMTS端点后，即可在ArcMap中使用它。

### 将地图添加到ArcMap中

在ArcMap中开始:

1. 点击工具栏中的**Add Data**按钮打开 _Add Data_ 对话框。
2. 在对话框的上端，点击**Look in:** 旁边的箭头并选择**GIS Servers**。

    ![ArcMap添加数据对话框](/help/img/3rdparty/arcgis-desktop-gis-servers.png)

3. 双击**Add WMTS Server**打开 _Add WMTS Server_ 对话框。

    ![ArcMap添加WMTS服务器对话框](/help/img/3rdparty/arcgis-desktop-add-wmts-server.png)

4. 将您之前定义的WMTS端点URL复制到上端的**URL**区域。
5. 在 _Server Layers_ 部分，点击**Get Layers**。当提示需要用户名和密码时，点击**Cancel**。您可能需要多次点击来取消这个对话框。 

    ![ArcMap添加GIS服务器连接](/help/img/3rdparty/arcgis-desktop-gis-server-connection.png)

6. 当数据在窗口中加载时，点击**OK**。

    ![ArcMap添加WMTS服务器确认对话框](/help/img/3rdparty/arcgis-desktop-server-layers.png)

7. 您应该看到_Mapbox on api.mapbox.com_ 在**Add Data**的对话框中。双击它，并在下一个对话框中选择您的样式，之后点击**Add**。

    ![Mapbox样式在ArcMap地图预览窗口](/help/img/3rdparty/arcgis-desktop-streets-layer.png)

您应该看到您的地图在您的ArcMap工程中以图层形式出现。需要注意的是每个样式都需要被单独添加。

## 在QGIS中添加Mapbox地图

QGIS也能够从WMTS服务器中读取地图瓦片。首先，您要为将添加到QGIS的样式构建WMTS端点。接下来，您要将此WMTS端点添加到QGIS项目中。

### 构建WMTS端点

用于在QGIS中添加地图的WMTS端点需要遵循以下格式：

```
https://api.mapbox.com/styles/v1/YOUR_USERNAME/YOUR_STYLE_ID/wmts?access_token={{ <UserAccessToken /> }}

```

您需要更改此URL中的三个部分：
1. **Mapbox用户名:** 将"YOUR_USERNAME"替换为您的Mapbox用户名，您可以在您的[Mapbox Studio主页](https://www.mapbox.com/studio)中找到。
1. **Map样式ID:** 将"YOUR_STYLE_ID"替换为您要添加到ArcMap中的样式ID。 找到样式ID的方法:
    - 在您的[Mapbox Studio主页](https://www.mapbox.com/studio/)，从您的系列样式中找到正确的样式。
    - 点击{{<Icon name="menu" inline={true} />}}**Menu**按钮。
    - 点击{{<Icon name="clipboard" inline={true} />}}图标复制样式URL，它看起来像`mapbox://styles/YOUR_USERNAME/YOUR_STYLE_ID`。样式ID是这个URL的最后一部分。
1. **Mapbox访问口令:** 添加您的Mapbox访问口令，您可以在您的[Mapbox账户界面](https://www.mapbox.com/account)找到。

当您使用用户名、样式ID和访问口令自定义WMTS端点后，即可在QGIS中使用它。

### 将地图添加到QGIS中

将Mapbox地图添加到QGIS中:

1. 在QGIS中点击**Add WMS/WMTS**按钮。

    ![QGIS从WTMS服务器中添加图层](/help/img/3rdparty/qgis-add-layer-from-server.png)

2. 确保对话框中的 _Layers_ 标签被选中。在对话框上端的下拉菜单下方，点击**New**。
3. 给图层命名并添加您之前自定义的WMTS端点URL。点击**OK**。

    ![QGI创建一个新的WMS连接](/help/img/3rdparty/qgis-create-wmts-connection.png)

4. 返回到 _Add Layer(s) from a WM(T)S Server_ 对话框，您的图层名称应该出现在对话框的上端。当您看到它，点击**Connect**。

    ![QGIS图层确认](/help/img/3rdparty/qgis-wmts-tileset.png)

5. _Tilesets_ 标签应该在一个单独的对话框中打开。选择该图层并点击**Add**，之后点击**Close**关闭对话框。

    ![完成使用Mapbox样式的QGIS地图](/help/img/3rdparty/qgis-wmts-layer.png)

您应该可以看到您的地图在您的QGIS工程中以图层形式出现。需要注意的是每个您想要展示的样式都需要被单独添加。

## 完成

您已使用WMTS端点将Mapbox样式添加到ArcMap或QGIS项目。
