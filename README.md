# 角色卡管理 · Mobile (Char Manager Mobile)

SillyTavern / TauriTavern 角色卡管理扩展的 **手机优化分叉**。

相对原版 [st-char-manager](https://github.com/idx425/st-char-manager)：

- **强制全深色 UI**：浅色酒馆主题下仍保持暗底亮字，避免白底黑字/看不清
- **手机弹层居中**：管理器 / 详情 / 文件夹弹窗居中显示，不顶到屏幕上方被裁切
- **safe-area 适配**：刘海屏与底部横条区域留白

与 [API 快切 (st-api-switcher)](https://github.com/idx425/st-api-switcher) 同一套视觉与定位体系。

> 原版桌面玻璃 UI 继续维护在 `st-char-manager`；本仓库专注手机端可读与居中。

## 功能

与原版一致：文件夹、分页、批量、接管原生角色面板、快捷栏、导入导出、详情补全浅数据、斜杠命令、自动更新提醒等。

## 安装

扩展面板 → **安装扩展 (Install extension)** → 粘贴：

```
https://github.com/idx425/st-char-manager-mobile
```

安装后刷新页面。扩展设置里显示为「角色卡管理 · Mobile」。

若已安装原版，可并存；设置键独立（`st_char_manager_mobile`），互不覆盖。

## 版本

- 当前：`3.1.0`
- 变更：强制全深色 + 手机弹层居中 + 独立仓库身份（更新检测指向本仓库）

## 环境要求

- SillyTavern 1.12+，TauriTavern 可用
- 收藏与最近记录存于本机酒馆设置，不修改角色卡文件本身
- 删除操作调用酒馆后端接口，不可恢复

## License

MIT
