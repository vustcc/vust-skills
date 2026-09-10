# Vue 3 Mapping

仅在目标是 Vue 3 时读取。

## 包与样式

```vue
<script setup lang="ts">
import { VustButton, VustInput } from "@vustcc/vue";
</script>
```

在项目全局样式入口导入当前版本公开的 Token 和 Vue 组件样式。以包 `exports`/README 为准。

## 映射

- 受控值使用必填 `modelValue` 与 `update:modelValue`；模板优先使用 `v-model`。
- Checkbox 同样使用 `modelValue`；不要套用 React 的 `checked` 契约。
- 自定义内容使用默认、具名或 scoped slots。
- 事件使用组件公开的 kebab-case 模板名称；读取 `.d.ts` 或源码确认事件负载。
- 模板属性沿用 Vue/HTML 名称，如 `class`、`readonly`、`maxlength`、`autocomplete`、`for`。
- 业务参数和传入配置对象字段保持共享契约的 camelCase，不为模板风格改写对象键。

## 页面骨架

```vue
<template>
  <div class="view-shell" data-page="example">
    <div class="view-toolbar" data-ui="toolbar">...</div>
    <div class="view-content" data-slot="content">...</div>
  </div>
</template>
```

## 项目适配

- 沿用项目现有 composables、状态管理、路由和 i18n；不要默认要求 Pinia 或固定 locale 文件。
- 在本地 `vust` 主控源码可用时，可参考现存的 `RuntimeLogView.vue`、`NodeManagerView.vue`、`FileEditorView.vue`、`TerminalView.vue` 或实际同类页面；先搜索确认路径，不把示例路径当契约。
- 运行目标项目声明的 Vue type-check、lint、test 和 build 命令。
