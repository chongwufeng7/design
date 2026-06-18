# TDesign for Mobile Community 设计规范

来源：[TDesign for mobile Community](https://www.figma.com/design/mCvVa2Samk687VXkeN6eU8/TDesign-for-mobile--Community-?node-id=0-1&p=f&t=ma75v7eEWpJX10cK-0)

本文档整理自 Figma 文件中的 `Styles 全局样式` 页面，用于后续产品设计引用。当前文件主要覆盖全局基础样式，包括色彩、色彩 Token、字体、圆角和投影；未包含完整业务组件规范。

## 1. 设计原则

TDesign 色彩和字体体系强调清晰层级、语义化引用和可替换的 Design Token。

- 先使用语义 Token，再落到具体色值。不要在业务设计中直接散用色阶。
- 组件 Token 应引用全局语义 Token，避免组件内部重复定义颜色规则。
- 字体层级遵循规律化字号和行高，保证移动端界面的可读性和节奏一致。
- 圆角、投影只用于表达组件层级和交互层级，不作为装饰性元素滥用。

## 2. 色彩系统

### 2.1 功能色

功能色分为四类：品牌色、错误色、警告色、成功色。每个功能色包含 10 级色阶，用于覆盖浅色背景、禁用、聚焦、悬浮、常态、点击等状态。

| 色阶 | Brand 品牌 | Error 错误 | Warning 警告 | Success 成功 |
| --- | --- | --- | --- | --- |
| 1 Light | `#F2F3FF` | `#FFF0ED` | `#FFF1E9` | `#E3F9E9` |
| 2 Focus | `#D9E1FF` | `#FFD8D2` | `#FFD9C2` | `#C6F3D7` |
| 3 Disabled | `#B5C7FF` | `#FFB9B0` | `#FFB98C` | `#92DAB2` |
| 4 | `#8EABFF` | `#FF9285` | `#FA9550` | `#56C08D` |
| 5 | `#618DFF` | `#F6685D` | `#E37318` | `#2BA471` |
| 6 | `#366EF4` | `#D54941` | `#BE5A00` | `#008858` |
| 7 | `#0052D9` | `#AD352F` | `#954500` | `#006C45` |
| 8 | `#003CAB` | `#881F1C` | `#713300` | `#005334` |
| 9 | `#002A7C` | `#68070A` | `#532300` | `#003B23` |
| 10 | `#001A57` | `#490002` | `#3B1700` | `#002515` |

建议状态映射：

| 状态 | Brand | Error | Warning | Success |
| --- | --- | --- | --- | --- |
| Light | 1 | 1 | 1 | 1 |
| Focus | 2 | 2 | 2 | 2 |
| Disabled | 3 | 3 | 3 | 3 |
| Hover | 6 | 5 | 4 | 4 |
| Normal | 7 | 6 | 5 | 5 |
| Click / Active | 8 | 7 | 6 | 6 |

### 2.2 中性色

| Token | 色值 |
| --- | --- |
| `White` | `#FFFFFF` |
| `Gray1` | `#F3F3F3` |
| `Gray2` | `#EEEEEE` |
| `Gray3` | `#E8E8E8` |
| `Gray4` | `#DDDDDD` |
| `Gray5` | `#C6C6C6` |
| `Gray6` | `#A6A6A6` |
| `Gray7` | `#8B8B8B` |
| `Gray8` | `#777777` |
| `Gray9` | `#5E5E5E` |
| `Gray10` | `#4B4B4B` |
| `Gray11` | `#393939` |
| `Gray12` | `#2C2C2C` |
| `Gray13` | `#242424` |
| `Gray14` | `#181818` |

### 2.3 文字和图标色

| Token | 色值 |
| --- | --- |
| `Font Gy1` | `#000000` / `90%` |
| `Font Gy2` | `#000000` / `60%` |
| `Font Gy3` | `#000000` / `40%` |
| `Font Gy4` | `#000000` / `26%` |
| `Font Wh1` | `#FFFFFF` / `100%` |
| `Font Wh2` | `#FFFFFF` / `55%` |
| `Font Wh3` | `#FFFFFF` / `35%` |
| `Font Wh4` | `#FFFFFF` / `22%` |

使用建议：

- 主要正文、标题：`Font Gy1`
- 次要说明、辅助信息：`Font Gy2`
- 占位符、弱提示：`Font Gy3`
- 禁用态文字：`Font Gy4`
- 深色或品牌色背景上的反白文字：`Font Wh1`
- 反白辅助文字按重要性使用 `Font Wh2`、`Font Wh3`、`Font Wh4`

## 3. 色彩 Token

TDesign 使用三层引用关系：

```text
基础色板 -> 全局语义 Token -> 组件 Token
```

示例：

| 基础色板 | 全局语义 Token | 组件 Token |
| --- | --- | --- |
| `blue-7` | `brand-color-hover: @blue-color-7` | `button-bg-hover: @brand-color-hover` |
| `blue-8` | `brand-color: @blue-color-8` | `button-bg: @brand-color` |
| `blue-9` | `brand-color-active: @blue-color-9` | `button-bg-active: @brand-color-active` |
| `white` | `bg-color-container: @white-color` | `table-bg: @bg-color-container` |
| `gray-1` | `bg-color-container-hover: @gray-color-1` | `table-bg-hover: @bg-color-container-hover` |
| `gray-3` | `bg-color-container-active: @gray-color-3` | `table-bg-active: @bg-color-container-active` |
| `fontgray-1` | `text-color-primary: @font-gray-1` | `menu-tabstext-select: @text-color-primary` |
| `fontgray-2` | `text-color-secondary: @font-gray-2` | `menu-tabstext: @text-color-secondary` |

### 3.1 中性色彩 Token

| Token | 描述 |
| --- | --- |
| `@bg-color-page` | 默认页面底层背景 |
| `@bg-color-container` | 主要容器背景、次要层级页面背景 |
| `@bg-color-secondarycontainer` | 次要容器背景 |
| `@bg-color-component` | 组件背景、主要容器之上组件背景 |
| `@component-stroke` | 默认组件分割线 |
| `@component-border` | 默认边框 |

### 3.2 中性色彩交互 Token

| Token | 描述 |
| --- | --- |
| `@bg-color-container-active` | 主要容器背景 click、次要层级页面背景 click |
| `@bg-color-secondarycontainer-active` | 次要容器背景 click |
| `@bg-color-component-active` | 组件背景 active、主要容器之上组件背景 active |
| `@bg-color-component-disabled` | 组件背景 disabled、主要容器之上组件背景 disabled |

### 3.3 文字与图标 Token

| Token | 描述 |
| --- | --- |
| `@text-color-primary` | 主要文字色彩 |
| `@text-color-secondary` | 次要文字色彩 |
| `@text-color-placeholder` | 占位符文字色彩 |
| `@text-color-disabled` | 文字 disabled 态 |
| `@text-colort-anti` | 文字反色色彩，源文件中如此命名 |
| `@text-color-brand` | 主题色文字色彩 |
| `@text-color-link` | 链接文字 |

### 3.4 主题色与功能色 Token

| Token | 描述 |
| --- | --- |
| `@brand-color` | 品牌色 |
| `@brand-color-active` | 品牌色 active |
| `@brand-color-disabled` | 品牌色 disabled |
| `@brand-color-focus` | 品牌色 focus |
| `@brand-color-light` | 品牌色 light |
| `@brand-color-light-active` | 品牌色 light 交互状态 active |
| `@error-color` | 错误色 |
| `@error-color-active` | 错误色 active |
| `@error-color-disabled` | 错误色 disabled |
| `@error-color-focus` | 错误色 focus |
| `@error-color-light` | 错误色 light 交互状态 |
| `@warning-color` | 警示色 |
| `@warning-color-active` | 警示色 active |
| `@warning-color-disabled` | 警示色 disabled |
| `@warning-color-focus` | 警示色 focus |
| `@warning-color-light` | 警示色 light 交互状态 |
| `@success-color` | 成功色 |
| `@success-color-active` | 成功色 active |
| `@success-color-disabled` | 成功色 disabled |
| `@success-color-focus` | 成功色 focus |
| `@success-color-light` | 成功色 light 交互状态 |

## 4. 字体系统

### 4.1 字体原则

TDesign 字体系统强调“好用、好记、美观”，目标是形成有规律、有韵律、像素对齐且层次明确的文字系统。

源文件 UIkit 覆盖 macOS 简体中文场景，默认字体为 `PingFang SC`。跨系统建议：

| 场景 | 字体建议 |
| --- | --- |
| macOS / iOS 简体中文 | `PingFang SC` |
| Windows 简体中文 | `Microsoft YaHei` |
| 英文或代码 | 按平台系统字体优先，代码可使用等宽字体 |

字重分为两类：

| 字重 | macOS | Windows |
| --- | --- | --- |
| 常规体 | `PingFang SC Regular` | `Microsoft YaHei Regular` |
| 加粗体 | `PingFang SC Semibold` | `Microsoft YaHei Bold` |

### 4.2 字号与行高

源文件规则：`line-height = font-size + 8`。其中 10px 字号在源文件中展示为 16px 行高。

| Token | 字号 | 行高 |
| --- | --- | --- |
| `@font-size-displayLarge` | `64px` | `72px` |
| `@font-size-displayMedium` | `48px` | `56px` |
| `@font-size-headlineLarge` | `36px` | `44px` |
| `@font-size-headlineMedium` | `28px` | `36px` |
| `@font-size-headlineSmall` | `24px` | `32px` |
| `@font-size-titleExtraLarge` | `20px` | `28px` |
| `@font-size-titleLarge` | `18px` | `26px` |
| `@font-size-titleMedium` | `16px` | `24px` |
| `@font-size-titleSmall` | `14px` | `22px` |
| `@font-size-bodyLarge` | `16px` | `24px` |
| `@font-size-bodyMedium` | `14px` | `22px` |
| `@font-size-bodySmall` | `12px` | `20px` |
| `@font-size-bodyExtraSmall` | `10px` | `16px` |
| `@font-size-markLarge` | `16px` | `24px` |
| `@font-size-markMedium` | `14px` | `22px` |
| `@font-size-markSmall` | `12px` | `20px` |
| `@font-size-markExtraSmall` | `10px` | `16px` |
| `@font-size-linkLarge` | `16px` | `24px` |
| `@font-size-linkMedium` | `14px` | `22px` |
| `@font-size-linkSmall` | `12px` | `20px` |

使用建议：

- 页面主标题：`headlineSmall` 到 `headlineLarge`
- 模块标题、列表标题：`titleSmall` 到 `titleExtraLarge`
- 常规正文：`bodyMedium`
- 次要说明：`bodySmall`
- 徽标、标签、辅助标记：`markSmall` 到 `markMedium`
- 链接文字：按正文层级使用对应 `link` token

## 5. 圆角

| Token | 值 | 场景 |
| --- | --- | --- |
| `@radius-small` | `3px` | 极小组件，元素高度小于 28px 时使用，例如徽标、标签 |
| `@radius-default` | `6px` | 常规组件，例如按钮、输入框、标签 |
| `@radius-large` | `9px` | 卡片，例如单元格组的非通栏卡片样式 |
| `@radius-extraLarge` | `12px` | 面板，例如对话框、弹出层、选择器 |
| `@radius-round` | `999px` | 胶囊型组件 |
| `@radius-circle` | `50%` | 圆形组件 |

## 6. 投影

| Token | 层级 | 场景 | CSS |
| --- | --- | --- | --- |
| `@td-shadow-1` | 基础投影 | 组件 hover 状态，例如表格和树拖动 | `0 1px 10px rgba(0, 0, 0, 5%), 0 4px 5px rgba(0, 0, 0, 8%), 0 2px 4px -1px rgba(0, 0, 0, 12%)` |
| `@td-shadow-2` | 中层投影 | 下拉组件，例如下拉菜单、气泡确认框、选择器 | `0 3px 14px 2px rgba(0, 0, 0, 5%), 0 8px 10px 1px rgba(0, 0, 0, 6%), 0 5px 5px -3px rgba(0, 0, 0, 10%)` |
| `@td-shadow-3` | 上层投影 | 警示或弹窗组件，例如全局提示、消息通知 | `0 6px 30px 5px rgba(0, 0, 0, 5%), 0 16px 24px 2px rgba(0, 0, 0, 4%), 0 8px 10px -5px rgba(0, 0, 0, 8%)` |

## 7. 设计使用清单

新建产品页面或组件时，按以下顺序引用规范：

1. 确定语义：品牌、错误、警告、成功、中性背景、文字、边框或交互状态。
2. 优先选择全局语义 Token，不直接选择色阶。
3. 组件内部再派生组件 Token，例如 `button-bg`、`table-bg-hover`。
4. 字体先确定层级，再选择字号 token 和字重。
5. 圆角按组件尺寸和容器层级选择，不随意新增半径。
6. 投影只用于 hover、浮层、弹窗等真实层级变化。
7. 若产品需要暗色模式，应新增独立模式 token，不覆盖 Light Mode 色值。

## 8. 待补充范围

这份 Figma 文件当前未系统展示以下内容，后续产品落地时建议另建规范补齐：

- 间距系统和栅格系统
- 图标尺寸、线宽、命名规范
- 常用移动端组件，如按钮、输入框、导航、列表、弹窗、表单、反馈组件
- 组件状态矩阵，如 default、hover、active、disabled、loading、error
- 暗色模式完整 token
- 无障碍对比度要求和最小触控区域
