# Manifest V3 升级说明

## 主要变化

### 1. manifest.json 更新
- `manifest_version` 从 2 升级到 3
- `background.scripts` 改为 `background.service_worker`
- 移除了 `webextension-polyfill` 依赖
- 添加了 `host_permissions` 字段来明确指定需要访问的网站

### 2. background.js 更新
- 从 background scripts 改为 service worker
- 将 `browser.*` API 调用改为 `chrome.*` API 调用
- 移除了 webextension-polyfill 依赖

### 3. content.js 更新
- 将 `browser.*` API 调用改为 `chrome.*` API 调用
- 移除了 webextension-polyfill 依赖

### 4. package.json 更新
- 移除了 `webextension-polyfill` 开发依赖

## 兼容性说明

- Manifest V3 原生支持 Chrome Extension API，无需 polyfill
- 所有功能保持不变
- 支持 Chrome 88+ 版本

## 安装说明

1. 删除 `node_modules` 文件夹（如果存在）
2. 运行 `npm install` 安装依赖
3. 在 Chrome 浏览器中加载扩展：
   - 打开 `chrome://extensions/`
   - 启用"开发者模式"
   - 点击"加载已解压的扩展程序"
   - 选择项目文件夹

## 功能特性

- 支持从以下网站一键添加豆瓣条目：
  - 音乐：Discogs、Bandcamp、Apple Music
  - 电影：IMDB
  - 游戏：Steam
- 自动填充表单信息
- 下载封面图片 