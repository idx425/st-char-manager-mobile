# 角色卡管理 · Mobile (st-char-manager-mobile)

SillyTavern 角色卡管理扩展的手机优化版。功能与 [st-char-manager](https://github.com/idx425/st-char-manager) 同步，额外针对触屏与窄屏：

- 隐藏原生热切换栏，平滑提拉角色名与 Token 计数，省出顶部空间
- 彻底移除高频 JS 布局轮询 (`pin()`)，全 CSS 零抖动响应式网格 (Zero-Jitter Engine)
- 修复手机标签栏/文件夹栏左右流畅划动
- 顶部快捷栏支持折叠，解决卡片位置靠下、无法向上划看全内容的问题
- 修复重启酒馆后创建的文件夹消失问题
- 支持 **紧凑模式 (Compact)** 与 **浅色/暗色主题**

## 安装

扩展 URL：

```
https://github.com/idx425/st-char-manager-mobile
```

## 更新日志

### v5.8.0 (最新修复版)
- **隐藏原生热切换栏 (`#CharListButtonAndHotSwaps`)**：接管原生角色面板时，自动隐藏顶部的 `:三` 按钮与 `★ 收藏角色以将它们添加到快速热切换区` 提示栏，将当前角色名与 Token 计数整体平滑向上提拉，释放顶部高度，同时确保不误伤顶栏主导航抽屉图标。
- **手机端零抖动优化 (Zero-Jitter Engine)**：
  - 彻底移除高频 JS 布局重绘函数 (`pin()`)，全面改用高性能 CSS `@media` 响应式网格布局，彻底消除屏幕旋转、拉起与切卡时的界面闪烁与卡顿。
  - 彻底重构 `.ccm-overlay` 弹窗与 `.ccm-modal-box` 硬件加速过渡动画，消除 CSS `transform: none !important` 与 `@keyframes` 冲突导致的开合帧跳跃。
  - 移除卡片原图 `will-change: transform`，降低 GPU 图层合成开销，提升手机大图列表滚动流畅度。
  - 防抖处理主题切换监听器 `checkThemeChanged()`，避免高频 DOM 变量刷新引发全页重排 (Reflow) 与抖动。
  - 优化切卡时的抽屉平滑关闭逻辑 (`closeCharDrawer()`)，消除多重定时器连续触发 click 导致的动画重叠抖动。
- **修复 DOM 重复 ID Bug**：修复 `openManager()` 弹窗中重复渲染 `id="ccm_toggle_edit_btn"` 按钮图标的问题。
- **手机端深度适配**：手机端默认 2 列自适应网格，触屏优化，完美适配 iOS Safari 与 Android Chrome，无缝兼容 ST 酒馆 (SillyTavern) 与 TT 酒馆 (TauriTavern)。

### v4.5.1
- **对照 ST 酒馆与 TT 酒馆源码全面审计后的修复版**
- **修复「删除的标签重启后复活」**
- **修复标签同步性能问题与删卡残留**

## License

MIT
