# API Document
- [http://192.168.0.141/mapCore/v2/docs/](http://192.168.0.141/mapCore/v2/docs/)

## Bower Download
``` bash
bower install http://192.168.0.51/bower/mapcore-core.git
```

## 使用
```html
<script src="http://192.168.0.51/bower/mapcore-core/raw/v23/mapCore.js"></script>
<script>
mapCore.loader(loadConfig, function(addMap) {
  addMap(mapConfig).then(map) {
    // map.addLayer('tile')...
  }
})
</script>
```

