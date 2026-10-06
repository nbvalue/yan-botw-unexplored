

# yan botw unexplored

BotW（塞尔达传说 旷野之息）存档查漏地图的 **PC 网页版**，把 Switch homebrew [lud99/botw-unexplored](https://github.com/lud99/botw-unexplored) 的解析逻辑完整移植到浏览器。

**在线演示：https://nbvalue.github.io/yan-botw-unexplorered/**

## 功能

- 手动载入存档 `game_data.sav`（按钮选择或直接拖入窗口）
- 载入后**只显示未收集 / 未击败 / 未发现**的内容
- 图层开关（与 Switch 版图例一致，使用原版图标）：
  克洛格种子 900 · 祠堂 120 · DLC 祠堂 16 · 地点 187 · 独眼巨人 40 · 岩巨人 40 · 莫尔德盖拉 4
- 滚轮缩放（以鼠标为锚点）、鼠标拖动平移、悬停查看详情
- 点击标记 = 标记为已完成，进度自动保存在浏览器（localStorage），关机不丢
- 克洛格寻找路径（97 条白色线路）
- 自动检测是否拥有 DLC
- 大师模式：载入 6/7 号槽位的存档即可

## 使用

访问在线演示，或下载本仓库后直接双击 `index.html`（纯静态、零依赖、可离线使用，存档数据全程在本地浏览器解析，不上传任何服务器）。

存档文件位置（Switch SD 卡）：

```
switch/botw-unexplored/saves/<用户UID>/<槽位>/game_data.sav
```

槽位 0-5 为普通模式，6-7 为大师模式。

## 技术说明

- 存档解析逻辑逐段移植自 lud99 的 `SavefileIO.cpp`：从 `0x0c` 起每 8 字节扫描 flag hash，值非 0 即已完成
- 全部数据表（坐标 + hash）从其 `Data.cpp` 提取，克洛格路径数据与 [d4mation/botw-unexplored-viewer](https://github.com/d4mation/botw-unexplored-viewer) 同源
- 地图底图与分类图标取自原项目 romfs 资源
- Canvas 渲染引擎：滚轮缩放、拖动平移、点击命中检测均为原生实现

## 致谢

- [lud99/botw-unexplored](https://github.com/lud99/botw-unexplored)（Switch 版原作）
- [d4mation/botw-unexplored-viewer](https://github.com/d4mation/botw-unexplored-viewer)（网页版先驱）
- [marcrobledo/savegame-editors](https://github.com/marcrobledo/savegame-editors)、MrCheeze 的 BotW 数据挖掘

> AI生成
