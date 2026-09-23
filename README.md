# 莲下随心游

> 一款聚焦本地文化、风景、美食与特色商家的微信小程序：以一张手绘文旅地图为主入口，把地方景点、餐饮商家、名小吃与地方影像整理成可浏览、可查看、可导航的内容集合。

「莲下随心游」使用 uni-app（Vue 3）开发并编译为微信小程序，面向想了解或到访本地的用户。用户可以在手绘地图上缩放、拖动查找景点与商家，点开查看图文详情并直接唤起手机地图导航；也可以浏览地方文化视频与本地小吃的图文介绍。项目不依赖后端服务，内容以本地数据文件配合 CDN 静态资源组织，整体体量轻、加载直接。

当前收录内容：**30 处文旅地点 · 26 家特色商家 · 10 种名小吃 · 8 条地方视频**。

## ✨ 功能

### 首页与简介

- 全屏图文首页：手绘底图、页面标题字与 IP 形象动图组合呈现
- 「简介」按钮唤起详情弹窗，展示地方简介长图，支持关闭
- 第二个入口按钮跳转「莲下风采」视频页
- 底部 tabBar 提供四个入口：简介 / 美景 / 名店 / 小吃，图标为项目自制图片

### 莲下风采

- 以列表形式展示 8 条地方文化视频的封面与标题
- 点击封面在列表内直接播放，未播放的条目显示封面并叠加深色遮罩与播放标识
- 页面滚动使当前视频移出可视区域时自动暂停播放，离开页面时重置播放状态

### 莲下美景

- 以手绘文旅地图为底图，基于 `movable-area` / `movable-view` 实现缩放（2.65x–5x）与拖动浏览
- 地图上标注 30 处可点击地点，涵盖公园、宗祠、古厝、故居、石刻等类型
- 点击地点弹出详情：图片轮播、文字介绍、地址信息
- 点击地址调用 `uni.openLocation` 唤起系统地图，直接导航至该地点

### 莲下名店

- 使用与「美景」一致的地图交互方式，覆盖 26 家本地餐饮商家
- 详情弹窗展示商家名称、图片轮播、简介、地址，并在右下角标注图片来源
- 一键唤起地图导航到店

### 莲下十大名小吃

- 展示 10 种本地小吃的图文列表，条目图片与名称并列排布
- 点击条目弹出详情：小吃名称、图片轮播、特色介绍与可选店家
- 介绍文本以 HTML 富文本形式存储，通过 `v-html` 渲染，便于保留加粗等排版

### 通用能力

- **分享**：所有页面在 `onLoad` 中注册 `uni.showShareMenu`，并实现 `onShareAppMessage` / `onShareTimeline`，转发给朋友与分享到朋友圈均返回统一的分享标题与分享底图
- **弹窗**：详情统一由 `uni-popup` 提供，居中弹出并关闭过渡动画，弹窗内为可滚动的图文结构
- **图片轮播**：详情页图片展示使用封装组件 `cc-mySwiper`，自动轮播并带指示点

## 📱 页面展示

当前仓库未包含页面截图，**页面截图待补充**。建议按下列页面补充截图，统一存放于 `docs/screenshots/` 后在此处引用：

| 建议文件名 | 对应页面 | 展示重点 |
| --- | --- | --- |
| `home.png` | 首页 | 全屏底图、标题字、IP 形象与两个入口按钮 |
| `home-intro.png` | 首页 · 简介弹窗 | 简介长图弹窗与关闭交互 |
| `tourism.png` | 莲下美景 | 手绘地图整体效果与地点标注 |
| `tourism-detail.png` | 莲下美景 · 地点详情 | 图片轮播、文字介绍与地址导航入口 |
| `shop-detail.png` | 莲下名店 · 商家详情 | 商家名称、轮播图、简介与图片来源标注 |
| `food.png` | 莲下十大名小吃 | 小吃列表布局 |
| `food-detail.png` | 莲下十大名小吃 · 详情 | 名称、轮播图、特色介绍与可选店家 |
| `video.png` | 莲下风采 | 视频列表与播放状态 |

## 🛠️ 技术栈

| 技术 | 用途 |
| --- | --- |
| 微信小程序 | 目标应用平台，`manifest.json` 中配置 `mp-weixin` 与 `lazyCodeLoading` |
| uni-app | 跨端应用框架，页面、路由与小程序能力均通过 uni-app 组织 |
| Vue 3 | 组件与页面开发，入口使用 `createSSRApp` 创建应用实例 |
| JavaScript (ES Module) | 页面逻辑、数据文件与组件实现 |
| Vue SFC | 页面与组件的单文件结构（`template` / `script` / `style scoped`） |
| Vite 5 + `@dcloudio/vite-plugin-uni` | 本地开发与小程序编译 |
| SCSS | 部分页面样式与 `uni.scss` 全局样式变量 |
| uni_modules（`uni-popup` / `uni-transition` / `uni-scss`） | 弹出层与过渡动画组件 |
| `cc-mySwiper`（第三方 uni_modules 插件） | 详情弹窗内的图片轮播组件 |
| 小程序内置组件 | `movable-area` / `movable-view` 手势缩放拖动、`scroll-view` 滚动、`video` 播放 |

小程序能力使用情况（均在页面代码中实际调用）：`uni.showShareMenu`、`uni.openLocation`、`uni.getSystemInfo`、`uni.createVideoContext`、`uni.createSelectorQuery`、`uni.navigateTo`。

## 📂 项目结构

```text
.
├── pages/
│   ├── index/index.vue        # 首页 / 简介（含分享与弹窗）
│   ├── tourism/tourism.vue    # 莲下美景：文旅地图、地点详情、导航
│   ├── shop/shop.vue          # 莲下名店：地图选店、商家详情、导航
│   ├── food/food.vue          # 莲下十大名小吃：列表与详情
│   └── video/video.vue        # 莲下风采：地方视频列表与播放
├── static/
│   ├── json/                  # 页面展示数据：food / shop / tourism / video
│   ├── food/                  # 小吃页面标题图
│   └── tabBar/                # tabBar 图标（选中 / 未选中）
├── uni_modules/               # uni-popup、uni-transition、uni-scss、cc-mySwiper
├── App.vue                    # 应用入口，注册全局自定义字体
├── main.js                    # uni-app 入口（Vue 3 / Vue 2 条件编译）
├── pages.json                 # 页面路由、导航栏标题与 tabBar 配置
├── manifest.json              # 应用配置：名称、版本、mp-weixin appid 等
├── uni.scss                   # 全局 SCSS 样式变量
├── vite.config.js             # Vite 配置，接入 uni 插件
└── package.json
```

## 🔧 本地运行

1. 使用 HBuilderX 打开项目根目录（`pages/`、`App.vue`、`pages.json`、`manifest.json` 为工程主结构）。
2. 运行 → 运行到小程序模拟器 → 微信开发者工具，编译产物输出到 `unpackage/dist/dev/mp-weixin`。
3. 在微信开发者工具中导入 `unpackage/dist/dev/mp-weixin` 即可预览；也可用微信开发者工具直接打开该目录作为小程序项目。
4. `manifest.json` 中的 `mp-weixin.appid` 已写入一个小程序 appid，请替换为你自己的 appid 后再预览或发布。

补充说明：

- 项目没有后端与接口依赖，无需配置服务器域名。图片与视频均来自 `cdn.lianxia.top`，本地开发时微信开发者工具默认不校验合法域名（`manifest.json` 中 `urlCheck: false`）；真机发布前需在微信公众平台为该域名配置 request / downloadFile 合法域名。
- 仓库同时保留了 uni-app CLI 模板的 `package.json`、`vite.config.js` 与 `src/` 目录，当前应用代码位于仓库根目录，`src/` 未参与构建。

## 📦 数据与资源

- 页面数据集中放在 `static/json/`，以 CommonJS 模块形式导出（`let data = [...]` + `module.exports = { data }`），页面通过 `import` 引入后直接绑定到 `data`。

| 数据文件 | 条目 | 字段 |
| --- | --- | --- |
| `static/json/food.json` | 10 | `id`、`name`、`img`、`text`、`shop`、`imglist` |
| `static/json/shop.json` | 26 | `id`、`Name`、`Introduction`、`Address`、`lat`、`lng`、`imglist`、`from` |
| `static/json/tourism.json` | 30 | `id`、`Name`、`Introduction`、`Address`、`lat`、`lng`、`imglist`、`from` |
| `static/json/video.json` | 8 | `name`、`img`、`video`、`videoId` |

- `imglist` 为详情弹窗轮播图数组，每项包含 `image` 字段；`lat` / `lng` 用于 `uni.openLocation` 导航；`from` 用于标注图片来源。
- 注意：商家与地点数据中的 `lat` / `lng` 命名与实际含义相反（`lat` 存的是经度、`lng` 存的是纬度），页面在调用 `uni.openLocation` 时按实际值传参，维护数据时不要按字段名直译。
- 图片、视频等大体积素材未随仓库分发，全部指向自建 CDN `cdn.lianxia.top`；仓库内的 `static/tabBar/` 与 `static/food/` 仅存放 tabBar 图标与页面标题图。

## 📝 说明

- `App.vue` 以 base64 内嵌了一套自定义中文字体（`AaBMCQCQKS (Non-Commercial Use)`，版权归属 HanMeiHutong (XiaMen) Technology Co.,Ltd.），用于详情弹窗标题；该字体授权为非商用，如需商业使用请替换为其它字体。
- 地图页面中的地点名称标签以图片形式托管在 CDN，热区位置在页面内以绝对定位坐标维护，新增地点需同步调整数据与热区坐标。
- 仓库目前未包含开源许可证文件。
