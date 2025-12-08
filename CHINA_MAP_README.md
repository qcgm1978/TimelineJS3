# 中国地图可视化示例

本项目提供了基于 HTML 和 Leaflet 的中国地图可视化方案，包含静态地图和交互式地图两种展示方式。

## 文件结构

```
TimelineJS3/
├── doc/
│   └── China.png          # 中国地图图片
├── china-map-example.html # 中国地图可视化页面
└── CHINA_MAP_README.md    # 说明文档
```

## 使用方法

### 1. 直接在浏览器中打开

由于使用了 CDN 版本的 Leaflet 库，您可以直接在浏览器中打开 `china-map-example.html` 文件：

```bash
# 在 macOS 上
open china-map-example.html

# 在 Windows 上
start china-map-example.html

# 在 Linux 上
xdg-open china-map-example.html
```

### 2. 功能介绍

#### 静态地图
- 显示 `doc/China.png` 中的中国地图
- 支持保存图片功能
- 支持全屏查看功能

#### 交互式地图
- 使用 Leaflet 库创建的交互式地图
- 默认显示中国中心区域（坐标：35.8617°N, 104.1954°E）
- 标记了中国主要城市（北京、上海、广州、深圳、成都、杭州、武汉、西安）
- 支持以下交互功能：
  - 放大/缩小地图
  - 居中地图
  - 切换地图类型（标准地图、卫星图、混合图、地形）
  - 点击城市标记查看城市名称

## 技术实现

### 核心技术栈
- HTML5 + CSS3
- JavaScript (ES6+)
- Leaflet.js v1.9.4 (CDN 版本)

### 主要功能实现

1. **静态地图功能**：
   - 使用 `<img>` 标签直接加载 `China.png`
   - 实现图片保存功能（使用 `download` 属性）
   - 实现全屏查看功能（使用全屏 API）

2. **交互式地图功能**：
   - 使用 Leaflet 创建地图实例
   - 设置中国中心点坐标和初始缩放级别
   - 添加多种地图图层（OpenStreetMap、Esri 卫星图等）
   - 添加城市标记并绑定弹出窗口
   - 实现地图控制功能（缩放、居中、切换图层）

## 自定义修改

### 修改静态地图图片

如果您想使用其他中国地图图片，只需将图片替换为 `doc/China.png`，或者修改 HTML 文件中的图片路径：

```html
<img id="static-map" src="./doc/China.png" alt="中国地图">
```

### 添加更多城市标记

在 JavaScript 代码中找到 `cities` 数组，添加新的城市坐标：

```javascript
const cities = [
    { name: '北京', lat: 39.9042, lng: 116.4074 },
    { name: '上海', lat: 31.2304, lng: 121.4737 },
    // 添加更多城市
    { name: '城市名称', lat: 纬度, lng: 经度 }
];
```

### 调整地图样式

您可以修改 CSS 样式来自定义地图页面的外观：

- 修改容器宽度：`.container { max-width: 1200px; }`
- 修改地图高度：`#interactive-map { height: 400px; }`
- 修改按钮颜色：`.controls button { background-color: #e74c3c; }`

## 浏览器兼容性

- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## 注意事项

1. 确保 `doc/China.png` 文件存在且路径正确
2. 由于使用了外部 CDN，需要确保网络连接正常
3. 交互式地图依赖于 Leaflet 库和第三方地图服务

## License

本项目使用 MPL-2.0 许可证，与 TimelineJS3 项目保持一致。