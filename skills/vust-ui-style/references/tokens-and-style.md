# VDL Tokens And Style

## 事实来源

- 使用消费项目当前安装版本的 `@vustcc/tokens` 公开 CSS 入口。
- 已安装包可读时，从其导出 CSS 获取准确 Token；本地 `vust-ui` 源码只作开发补充。
- 沿用消费项目已有全局重置、滚动条、壁纸和主题切换层，不把业务适配写回公共 Token。
- Token 不存在时先查当前包是否有近似语义；确需新增时在可写 UI 源码仓完成并发布。

## 常用语义

- 背景：`--vdl-bg-canvas`、`--vdl-bg-base`、`--vdl-bg-panel`、`--vdl-bg-card`、`--vdl-bg-muted`、`--vdl-bg-input`
- 文本：`--vdl-text-primary`、`--vdl-text-secondary`、`--vdl-text-muted`、`--vdl-text-subtle`、`--vdl-text-inverse`
- 品牌与状态：`--vdl-primary`、`--vdl-secondary`、`--vdl-accent`、`--vdl-success`、`--vdl-warning`、`--vdl-danger`、`--vdl-info`
- 边框：`--vdl-border-subtle`、`--vdl-border-default`、`--vdl-border-strong`、`--vdl-border-brand`
- 字体：`--vdl-font-family`、`--vdl-font-mono` 及当前版本字号 Token
- 结构：当前版本的 `--vdl-space-*`、`--vdl-radius-*`、`--vdl-z-index-*`

本清单是导航，不保证旧版本包含所有 Token。写代码前检查已安装 CSS。

## 使用规则

- 使用语义 Token，不散落硬编码颜色、阴影和 z-index。
- 固定状态语义：成功/在线用 success，等待/风险提示用 warning，失败/删除用 danger，通信/扫描/提示用 info 或 primary。
- 日志、ID、路径、命令、哈希、端口和 IP 使用等宽字体。
- 工具栏与紧凑表单使用较小间距，主内容使用稳定边距；不要让同一色相统治页面。
- 浅色和深色主题分别检查文本、图标、边框、状态和浮层遮罩对比度。

## 布局约束

- 窗口根通常使用 `height: 100%`、`min-height: 0` 和纵向 flex。
- 可滚动子项设置 `min-height: 0`，防止表格、日志、编辑器或终端撑破窗口。
- 表格列、工具栏按钮、图表、编辑器和终端设置合理的稳定尺寸或 min/max 约束。
- 长文本不能溢出按钮、Tag 或单元格；使用截断、Tooltip、换行策略或详情 Dialog。
