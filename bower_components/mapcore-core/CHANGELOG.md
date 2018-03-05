## 2.3.0
  - API
    - 新增
      - 新增 mapCore.loader
      - 加入產生聯集(union)、差集(difference)、交集(intersect) geomtry 功能
      - 加入計算最接近點坐標/點位(nearest)
      - 加入產生 polygeometry 移動後的 geometry 功能(move)
      - groupOption 新增 maxZoom, minZoom 選項
      - 新增 image show/hide 功能
      - 新增 maoCore.tools.toGeoJSON, tools.toGeometry 功能 //beta
      - 掛載部份 turf 功能 (mapCore.turf) //beta
    - 修正
      - 修正screenPoint 轉 geometry 在 4326 坐標系統計算錯誤問題
      - layerOption / groupOption 補上 default value({})
      - mapCore.coordTrans 功能移至 mapCore.tools.coordTrans
      - 調整 jsdoc 寫法，加入繼承 & mapCore namespace
      - polygonGeometry 定義為 2 or 3 dimension
      - holePolygonGeometry 定義為 3 dimension
      - multiPolygonGeometry 定為為 4 dimension
    - 移除
      - 移除舊 EventAPI(改以 .on, .off, .trigger 代替)
      - 移除 addHolePolygon, addMultiPolygon API
  - 其它
    - 版號因 core 與 esri/google 分離，直接跳號至2.3
    - 打包方式由 AMD 改為 UMD
## 0.4.13
  - 新增 addFeature, addCluster, addHeatMap api
  - holePolygon geometry 判斷修正
  - 新增 mapCore.wrap 功能
  - 新增 getOriginInfo innerAPI
  - nearby unit 新增 px
  - nearby 加入 (polyline, polygon, circle 判斷)
  - 新增 map.sync, group.sync api 同步原生資料
  - mapCore 新增 exportStore, importStore API
  - Graphic 新增 holePolygon, multiPolyline, multiPolygon Type
  - Graphic geometry 新增 sr, type屬性
  - order 排序方式調整 (setOrder 只設定不排序)
  - jsdoc 說明文件調整
  - 移除 map 物件下的 _layers, _groups, _graphics, _images 屬性
  - setBaseLayer option.id 修正
  - dms toDecimal 回傳由 String 修正為 Number
  - 調整 MapCore.version 為物件格式
  - 新增 MapCore.tools.getBound: 取得 (3825,3826,3827,3828) bound
  - 新增 MapCore.tools.toDegree: 經緯度 轉 度分秒
  - 新增 MapCore.tools.toDecimal: 度分秒 轉 經緯度
  - 新增 MapCore.tools.coordTrans: 坐標轉換
  - 新增 coordTrans SR 合理範圍檢查功能
  - 新增傳入 geometry 範圍與 config.mapSet.sr 檢查
  - on 新增 eventOption: {name: ''}
## 0.4.12
  - 修正 esri 沒有預設底圖時，未回傳 map 物件問題
## 0.4.11
  - 升級 coordTrans 套件
## 0.4.10
  - fix promise resolve 錯誤判斷
## 0.4.9
  - innerAPI: 新增 moveToFront (graphic)
  - outerAPI: 新增 graphic.bringToFront
  - innerAPI 檢查提醒改為 console.warn
  - config 初始值調整
## 0.4.8
  - mapConfig 會在 core deep clone
  - graphic 新增 outerAPI: getBuffer
  - graphic/group/map 新增 outerAPI: nearby
## 0.4.7
  - 新增 Array.prototype coordTrans 擴充
  - 新增 event 傳入 evt object
## 0.4.6
  - 新增 WMTSLayer 類別
  - 新增 innerAPI: setWMTSLayer
  - map 新增 pan , panstart 事件
## 0.4.5
  - 預設關閉 debug mode
  - 新增 innerAPI: toScreenPoint、toPointGeometry
  - 新增 map.id 屬性
## 0.4.4
  - 移除 map loaded 事件
  - 新增 debug mode (mapCore.debug)
  - 新增 setNativeMapType 事件 (for ESRI)
  - mapCore.create() 新增 mapTypeID 參數
## 0.4.3
  - setBaseLayer 完成事件綁定處理
  - 恢復 cache layerType 改名為 wmts_hex
## 0.4.2
  - 新增 outerAPI: addLayerType
  - 新增 innerAPI: addLayerType
## 0.4.1
  - event bug fix
## 0.4.0
  - 新增 全新的 Event 處理機制
  - 移除 innerAPI: startEvent, stopEvent
  - 調整 addMarker default url
## 0.3.7
  - fix setGroupListIndex, setLayerListIndex indexSort 傳入錯誤 object
  - feature indexList 改為 indexObj
  - feature orderList 改為 orderObj
## 0.3.6
  - feature mapCore extend 機制調整(原 fn)
  - feature 新增 WMSLayer Class
  - feature 新增 wmsLayer.setWMSLayer()
  - feature Group 新增 unFocus()
  - feature Group 移除 focus:on focus:reset 事件
  - fix graphic.focus 傳入 symbol 時繼承問題
  - fix labelSymbol "backgroundColor" typo error
  - fix layerOption "tileSize" type error
## 0.3.5
  - 異動 innerAPI: setDynamicLayer 若要更換 layer.origin 回傳 _layer，不然就回傳 undefined
  - 異動 innerAPI: setBaseLayer 參數多一個 _oldMap，若有更換 map.origin 才有值
## 0.3.4
  - 新增 innerAPI: newMap
  - 修正 getLayerList, getGroupList, setLayerList, setGroupList 傳入 this 對應錯誤問題
  - 異動 innerAPI: setBaseLayer 新增 isRebuild 參數
  - 異動 innerAPI: setNativeMapType 回傳值調整為 _map 或 undefeind
  - 移除 innerAPI: rebuildMap, getMethod, getStatus
## 0.3.3
  - 新增 rebuildMap (innerAPI)
## 0.3.2
  - 改名
    - setMapType 改名為 setNativeMapType (outerAPI & innerAPI)
    - setGroupOrder 改名為 setGroupListOrder (outerAPI)
    - setGroupIndex 改名為 setGroupListIndex (outerAPI)
    - setLayerOrder 改名為 setLayerListOrder (outerAPI)
    - setLayerIndex 改名為 setLayerListIndex (outerAPI)
  - 異動
    - attribute type 由 Any 改為 Object
  - 移除
    - findGraphic (innerAPI)
  - Bugfix
    - order / index 排序問題修正
## 0.3.1
  - 異動
    - group.setEvent callback 再包裝過 (將原生 graphic 對應到 Graphic 物件)
  - 移除
    - getStatus, getMethod (innerAPI)
  - Bugfix
    - 修正 openInfoWindowByAny 傳入參數錯誤
## 0.3.0
  - 重大調整
    - 初始化方式由 Core.map(init, divID, config, innerAPI) 改為 Core.create(innerAPI)(init, divID, config)
  - 新增
    - 加入 plugin 擴充機制
    - 加入 mapCore 全域變數
    - 針對不需要的 innerAPI 進行檢查
  - 異動
    - setEvent callback 中的 this 改為該實體
    - 調整 findGraphic 為全域搜尋
  - Bugfix
    - 修復 setBaseLayer 功能
## 0.2.4
  - 異動
    - imageOption 暫時調整成跟 graphicOption 相同
    - layerOption.index 改為 >= 0, default 為 undefined
    - layerOption.order 改為 >= 0, default 為 0
  - Bugfix
    - 修復 LayerEvenType wmsChange 錯誤 (應為 wmschange)
    - 修復 setIndex 排序錯誤問題
    - openInfoWindowByAny 傳入 innerAPI 參數錯誤修正
## 0.2.3
  - feature
    - 更名 outerAPI setLayerList 改為 setLayerIndex
    - 更名 outerAPI setGroupList 改為 setGroupIndex
    - 新增 innerAPI setGraphicEvent
    - 新增 outerAPI setLayerOrder
    - 新增 outerAPI setGroupOrder
    - 新增 outerAPI layer.fire, group.fire
    - 新增 outerAPI graphic.setEvent
    - 新增 graphicEventType (和 GroupEventType 相同)
    - 新增 infoWindowOption
    - 異動 outerAPI addLayer 為 image 時，不需傳入 layerURL
    - 異動 innerAPI removeEvent 不再傳入 id
    - 異動 innerAPI fire 不再傳入 target(eventID)
    - 異動 inner & outerAPI setExtent 傳入參數 (xmin, ymin, xmax, ymax, spatialReference ) 調整為 ( extent, spatialReference )
    - 異動 graphicOption.infoWindow 預設值改為 infoWindowOption
    - 移除 GroupEventType 中的 focus:click, focus:mouseover
  - fix
    - 修復 graphic.setSymbol 原本設定值會被覆蓋的問題
    - 修復 map.addLayer('image') 出現 layerURL 不存在的錯誤
## 0.2.2
  - feature
    - graphicOption.infoWindow 預設值由 {} (空物件) 改為 '' (空字串)
    - 調整 jsdoc 說明
## 0.2.1
  - feature
    - outerAPI input/output 皆已經過測試
    - Event 相關 innerAPI 不再傳入 eventID
    - 加入 order 判斷
  - fix
    - 修正 map.removeLayer 下，dynamicLayer 無法移除問題
## 0.2.0
  - 重大調整
    - innerAPI 的 this 不另外做包裝，直接使用 原生的資料
  - change
    - event.listen -> event.start
## 0.1.9
  - add
    - outerAPI 新增 layer.show / layer.hide / group.show / group.hide API (取代 setVisible)
    - innerAPI 新增 stopEvent, startEvent
  - change
    - outerAPI graphic.unfocus 改名為 graphic.unFocus
    - innerAPI zoomIn / zoomOut 移除
    - graphic.geometry -> graphic.setGeometry, graphic.getGeometry
    - graphic.attribute -> graphic.setAttribute, graphic.getAttribute
    - graphic.symbol -> graphic.setSymbol, garphic.getSymbol
  - fix
    - group.setVisible 對應 innerAPI 錯誤修正
    - 修復 setGraphicVisible 關閉會執行2次的問題
## 0.1.8
  - add
    - innerAPI 新增 zoomToGroup(原zoomToGraphic)
    - innerAPI 新增 panToGroup(原panToGroup)
    - innerAPI 新增 getGraphic(原getGraphicByID)
  - remove
    - innerAPI 移除 setGraphicAttribute
    - innerAPI 移除 getGraphicByID
  - fix
    - 修復 symbol 規則錯誤
    - 修復 graphicOption 規則錯誤
## 0.1.7
  - enhancement
    - 採用 airbnb eslint
  - feature
    - core setIndex, setOrder 功能完成
    - innerAPI 介面新增 setGroupEvent, getGroupList, clearGroup,
    - innerAPI 介面新增 getGroup, setGroupOpacity, setGroupEvent, setGroupVisible
  - remove
    - innerAPI 介面移除 setGraphicLayerEvent, getGraphicLayerList, clearGraphicLayer
    - innerAPI 介面移除 hasGraphic, getAttributeByID
  - 目前 test cover 約 70%
## 0.1.6
  - feature: inner API 新增 removeGroup, removeEvent
  - feature: inner API 移除 removeMapEvent, removeLayerEvent, removeGraphicLayerEvent
  - fix: map 物件 add graphic 回傳錯誤
  - fix: other bugs fix
## 0.1.5
  - feature: 加入 Map, Layer, Group 相關 Event API 對應
  - fix: this 傳入 inner API 錯誤
  - fix: bugs
## 0.1.4
  - feature: 向下相容 addLayer('graphic')
## 0.1.3
  - feature: 調整 innerAPI 實作介面
  - feature: 新增 dynamicLayer, imageLayer, Group, Graphic 回傳物件
## 0.1.2
  - feature: addLayer 改回傳 object
## 0.1.1
  - feature: 使用 ES6
  - feature: 統一 jsdoc ci 流程
## 0.1.0
  - init
