# React 19 Mapping

仅在目标是 React 19 时读取。

## 包与样式

```tsx
import { VustButton, VustInput } from "@vustcc/react";
```

在项目全局样式入口导入当前版本公开的 Token 和 React 组件样式。以包 `exports`/README 为准。

## 映射

- 受控值使用必填 `value` 与 `onChange`；Checkbox 使用原生语义 `checked`。
- 自定义内容使用 `children`、render 属性或公开回调，不使用 Vue slot 名称。
- DOM 属性使用 React 名称，如 `className`、`readOnly`、`maxLength`、`autoComplete`、`htmlFor`。
- ARIA 映射以当前组件类型声明为准；不要从 Vue 模板机械转换属性名。
- 配置对象字段与 Vue 共享业务契约，例如表格列可用 `renderCell`，但必须以安装版本类型为准。
- 保持 state 单一来源，回调更新消费方状态；不要在组件外复制一套失同步视觉状态。

## 页面骨架

```tsx
export function ExampleView() {
  return (
    <div className="view-shell" data-page="example">
      <div className="view-toolbar" data-ui="toolbar">...</div>
      <div className="view-content" data-slot="content">...</div>
    </div>
  );
}
```

## 项目适配

- 沿用项目现有 hooks、状态管理、路由和 i18n；不要擅自引入新的全局状态或路由库。
- 在 React 套件源码可用时，可搜索 `@vustcc/react` 的实际导入并参考同类页面；实例只用于项目约定，不覆盖安装包类型。
- 运行目标项目声明的 React type-check、lint、test 和 build 命令。
