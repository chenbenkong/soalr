# soalr（纯 HTML 版 3D 太阳系运行模型）

> 一个不依赖构建工具的 3D / 2D 太阳系模拟网页集合，Three.js 本地内置，浏览器直接打开即可运行。

## 项目简介

soalr 是一组 **纯静态、零构建** 的太阳系模拟网页。Three.js 及其 `OrbitControls` 已随仓库内置在 `vendor/` 目录中，因此无需 `npm install`、无需联网加载 CDN，直接双击 HTML 文件即可在浏览器中查看太阳系的运行。

## 功能特性

- **多版本演示**：同一项目提供 3D 与 2D 多种视角版本，便于对比与学习
  - `index.html`：3D 太阳系模拟（主入口）
  - `solar.html`：太阳系运行模拟
  - `solar_2D-002.html`：2D 视角太阳系运行模拟（俯视轨道视图）
  - `solar_3d_001.html` / `solar_3d_002.html`：3D 太阳系的其他变体演示
- **交互控制**：基于 `OrbitControls` 的鼠标拖拽旋转、滚轮缩放
- **本地资源**：`vendor/three.min.js` + `vendor/OrbitControls.js` + `vendor/textures/` 全部本地化，离线可用
- **免构建**：纯 `<script>` 引入，无打包步骤，适合快速预览与教学

## 技术栈

- **Three.js**（内置 `vendor/three.min.js`，本地引用，非 CDN）
- **OrbitControls**（`vendor/OrbitControls.js`）
- 原生 HTML / CSS / JavaScript，无框架、无构建工具

## 目录结构

```
soalr/
├── index.html            # 3D 太阳系模拟（主入口）
├── solar.html            # 太阳系运行模拟
├── solar_2D-002.html     # 2D 视角太阳系运行模拟
├── solar_3d_001.html     # 3D 太阳系变体
├── solar_3d_002.html     # 3D 太阳系变体
├── vendor/
│   ├── three.min.js       # Three.js 运行时（本地内置）
│   ├── OrbitControls.js   # 轨道控制器
│   └── textures/          # 行星贴图等静态资源
├── .nojekyll             # 关闭 GitHub Pages 的 Jekyll 处理
└── LICENSE
```

## 本地运行

无需安装任何依赖，直接用浏览器打开对应的 HTML 文件即可：

```bash
# 方式一：直接双击 index.html，或在文件管理器中打开
# 方式二：用本地静态服务器（可选，避免个别浏览器 file:// 限制）
python3 -m http.server 8000
# 然后浏览器访问 http://localhost:8000/index.html
```

推荐入口：`index.html`（3D 太阳系模拟）。

## 在线演示

<https://chenbenkong.github.io/soalr/>

## 说明 / 备注

- 仓库含 `.nojekyll`，使 GitHub Pages 正确托管 `vendor/` 等以下划线/特殊结构命名的资源。
- 由于 `three.min.js` 为本地内置，整个项目可完全离线运行，不依赖外网 CDN。
- 与同系列 React 工程（如 sy-826、solor-zipu、solar-est）相比，本仓库更轻量、更适合作为 Three.js 入门对照参考。
