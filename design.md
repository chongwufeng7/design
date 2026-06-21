# 设计决策

本规范根据 `fenpidaoru.md` 中全部 Figma 链接逐项读取整理，面向移动端产品设计与后续组件落地。整体设计语言采用 TDesign Mobile 风格：白色容器、品牌蓝主导交互、低饱和中性色承载层级，控件高度与圆角按移动端触控场景统一。

1. 视觉层级以「品牌色 + 文字透明度 + 分割线 + 投影」共同表达。主操作使用 Brand7 `#0052D9`，点击态使用 Brand8 `#003CAB`，弱强调区域使用 Brand1 `#F2F3FF`。
2. 字体族最高优先级使用思源黑体（简体中文），后备顺序为 PingFang SC、Microsoft YaHei、系统无衬线字体；常规文本 `Regular 400`，标题、选中态与关键数值使用 `Semibold 600`。行高遵循 `字号 + 8px` 的节奏。
3. 圆角按组件承载面分级：小标签 3px，按钮/输入框 6px，卡片 9px，弹层/Picker 12px，胶囊/圆形使用 999px 或 50%。
4. 触控组件优先保证高度：按钮 28/32/40/48，列表型输入与单选项 56，底部 TabBar 56，Picker/DatetimePicker 弹层宽 375、高 258。
5. Calendar、Picker、DatetimePicker 均以底部弹层为主要形态，顶部圆角 12px，确认按钮位于底部或头部右侧，适合单手操作。
6. Navbar 使用 `TD_navbar` 真实组件源，覆盖小程序、H5、搜索、图片、标题对齐、标题尺寸和自定义颜色等导航栏场景。

# Token

## 色彩

### 品牌色

| Token | 值 | 用途 |
| --- | --- | --- |
| Brand1-Light | `#F2F3FF` | 轻量背景、范围选中连续区域 |
| Brand2-Focus | `#D9E1FF` | 聚焦弱反馈 |
| Brand3-Disabled | `#B5C7FF` | 品牌按钮禁用、日历禁用今日 |
| Brand4 | `#8EABFF` | 扩展浅色阶 |
| Brand5 | `#618DFF` | 扩展色阶 |
| Brand6 | `#366EF4` | hover/过渡色 |
| Brand7-Normal | `#0052D9` | 主按钮、选中、链接主色 |
| Brand8-Click | `#003CAB` | 点击/按下态 |
| Brand9 | `#002A7C` | 深色扩展 |
| Brand10 | `#001A57` | 深色扩展 |

### 功能色

| 类型 | 色阶 |
| --- | --- |
| Error | `#FFF0ED`, `#FFD8D2`, `#FFB9B0`, `#FF9285`, `#F6685D`, `#D54941`, `#AD352F`, `#881F1C`, `#68070A`, `#490002` |
| Warning | `#FFF1E9`, `#FFD9C2`, `#FFB98C`, `#FA9550`, `#E37318`, `#BE5A00`, `#954500`, `#713300`, `#532300`, `#3B1700` |
| Success | `#E3F9E9`, `#C6F3D7`, `#92DAB2`, `#56C08D`, `#2BA471`, `#008858`, `#006C45`, `#005334`, `#003B23`, `#002515` |

常用语义：错误 normal `#D54941`、错误 click `#AD352F`、错误 disabled `#FFB9B0`；警告 normal `#E37318`、click `#BE5A00`；成功 normal `#2BA471`、click `#008858`。

### 中性色与文本

| Token | 值/透明度 | 用途 |
| --- | --- | --- |
| White | `#FFFFFF` | 容器、弹层、按钮文字 |
| Gray1 | `#F3F3F3` | Picker 指示条、弱底色 |
| Gray2 | `#EEEEEE` | 辅助底色 |
| Gray3 | `#E8E8E8` | 分割线 |
| Gray4 | `#DDDDDD` | 边框 |
| Gray5 | `#C6C6C6` | 禁用边框/浅图标 |
| Font Gy1 | `rgba(0,0,0,0.90)` | 主文字、标题 |
| Font Gy2 | `rgba(0,0,0,0.60)` | 次级文字 |
| Font Gy3 | `rgba(0,0,0,0.40)` | 占位、辅助 |
| Font Gy4 | `rgba(0,0,0,0.26)` | 禁用 |
| Font Wh1 | `#FFFFFF` | 深色背景文字 |

## 字体

字体族优先级：`Source Han Sans SC`, `思源黑体`, `PingFang SC`, `Microsoft YaHei`, system-ui, sans-serif。Figma 源文件中的 PingFang SC 作为视觉参考，实际落地以思源黑体（简体中文）为最高优先级。

| Token | 字重 | 字号/行高 | 用途 |
| --- | --- | --- | --- |
| Display Large | Semibold | 64/72 | 大展示 |
| Display Medium | Semibold | 48/56 | 展示标题 |
| Headline Large | Semibold | 36/44 | 一级标题 |
| Headline Medium | Semibold | 28/36 | 二级标题 |
| Headline Small | Semibold | 24/32 | 三级标题 |
| Title ExtraLarge | Semibold | 20/28 | 大标题 |
| Title Large | Semibold | 18/26 | 弹层标题 |
| Title Medium | Semibold | 16/24 | 控件标题、选中态 |
| Title Small | Semibold | 14/22 | 月份标题 |
| Body Large | Regular | 16/24 | 表单内容、按钮大号文本 |
| Body Medium | Regular | 14/22 | 次级文本、星期栏 |
| Body Small | Regular | 12/20 | 小号说明 |
| Body ExtraSmall | Regular | 10/16 | 徽标、日历附加信息 |
| Mark Large | Semibold | 16/24 | 强调文本、确认按钮 |
| Mark Medium | Semibold | 14/22 | 小按钮/标签 |
| Mark ExtraSmall | Semibold | 10/16 | TabBar 标签强调 |
| Link Large | Regular | 16/24 | 大链接 |
| Link Medium | Regular | 14/22 | 常规链接 |
| Link Small | Regular | 12/20 | 小链接 |

## 圆角

| Token | 值 | 用途 |
| --- | --- | --- |
| radius-small | 3px | 小标签、链接焦点热区 |
| radius-default | 6px | 按钮、输入框、日期单元、卡片选项 |
| radius-large | 9px | Cell Group、卡片式表单 |
| radius-extraLarge | 12px | Picker、Calendar、弹层顶部 |
| radius-round | 999px | 胶囊按钮、文字 FAB |
| radius-circle | 50% | 圆形按钮、圆形 FAB |

## 投影

| Token | 定义 | 用途 |
| --- | --- | --- |
| Shadow-1 基础投影 | `0 2px 4px -1px rgba(0,0,0,.12)`, `0 4px 5px 0 rgba(0,0,0,.08)`, `0 1px 10px 0 rgba(0,0,0,.05)` | 输入卡片、轻浮层 |
| Shadow-2 中层投影 | `0 5px 5px -3px rgba(0,0,0,.10)`, `0 8px 10px 1px rgba(0,0,0,.06)`, `0 3px 14px 2px rgba(0,0,0,.05)` | FAB |
| Shadow-3 上层投影 | `0 8px 10px -5px rgba(0,0,0,.08)`, `0 16px 24px 2px rgba(0,0,0,.04)`, `0 6px 30px 5px rgba(0,0,0,.05)` | TabBar 二层菜单/上层浮层 |

# 使用规则

1. 主按钮、选中态、确认态统一使用 Brand7；按下态切换 Brand8；禁用态使用 Brand3 或文字 Gy4。
2. 组件的状态必须成组设计：normal、active/press、disabled；输入类组件还需 success、warning、error。
3. 文本透明度用于表达信息优先级：主信息 Gy1，说明与未选 Gy2，占位 Gy3，禁用 Gy4。
4. 移动端控件最小可点区域建议不低于 28px，高频主控件优先 40px 或 48px。
5. 列表/表单场景使用 16px 左右内边距；卡片形态宽度以 343px 为 375px 屏幕下的基准。
6. 分割线使用 Gray3，移动端可用 0.5px；只有需要强化边界时使用 Gray4 1px 边框。
7. 底部弹层类组件固定白底、顶部圆角 12px，头部标题使用 Title Large，操作按钮靠左/右或底部全宽。
8. 日历和选择器的选中态必须同时使用文字字重变化与背景变化，避免只靠颜色表达。
9. Navbar 固定放置于内容区上方、系统状态栏下方；默认高度 48px，Large 标题样式高度 104px，标题、左侧操作和右侧操作需保持垂直居中。

# 组件规范

## Button 按钮

- 类型：Basic、Icon Button、Ghost、Block、Button Group。
- Variant：`base`、`outline`、`dashed`、`text`、`ghost`。
- Theme：`primary`、`light`、`default`、`danger`、`text`。
- Size：large 48px、medium 40px、small 32px、extraSmall 28px。
- Shape：rectangle、round、square、circle；square/circle 宽高相等。
- 默认圆角 6px，round/circle 使用 999px/50%。
- 主要颜色：primary normal `#0052D9`，active `#003CAB`，disabled `#B5C7FF`；light 背景 `#F2F3FF`；danger normal `#D54941`。
- Medium 文本按钮参考内边距 `16px 8px`，图标与文字间距 4-8px。

## FAB 浮动按钮

- 类型：纯图标、图标加文字。
- Theme：primary、default、light、danger。
- Shape：circle、square、round。
- Size：large 48px 图标 24px；medium 40px 图标 20px；small 32px 图标 18px；extraSmall 28px 图标 18px。
- 圆形 large 半径 24px；方形使用 6px；文字 FAB 胶囊半径 24px。
- 使用 Shadow-2，通常悬浮于页面内容之上，不参与普通列表流布局。

## Divider 分割线

- 类型：水平、带文本水平、垂直、虚线。
- 文本对齐：left、center、right。
- 颜色使用 Gray3 `#E8E8E8` 或 Gray4 `#DDDDDD`。
- 线宽移动端可用 0.5px，普通 Web/高密度场景可用 1px；垂直分割线示例高 14px。

## Link 链接

- 类型：基础链接、下划线链接、前置图标、后置图标。
- Theme：primary、default、danger、warning、success。
- State：normal、active、disabled。
- Size：large 16/24 搭配 18px 图标；medium 14/22 搭配 16px 图标；small 12/20 搭配 14px 图标。
- Active 色：primary `#003CAB`、danger `#AD352F`、warning `#BE5A00`、success `#008858`。
- Disabled 使用对应浅色阶；交互热区可参考 3px 小圆角。

## TabBar 标签栏

- 用途：底部功能模块切换。
- 类型：纯文本、图标加文本、纯图标、带徽标、双层菜单、带分割线。
- Item 数：2、3、4、5；整栏宽 375px，胶囊/内容宽示例 343px。
- Bar 高度 56px，内容内边距 8px，间距 8px。
- 选中态：普通模式使用品牌色文字/图标；tag 模式使用 Brand1 背景与 Brand7 文本。
- 未选中态使用 Font Gy1 或 Gy2；图标常用 20px；小标签文字使用 10/16。
- Badge 使用错误色 `#D54941`，圆点 8px，数字徽标最小宽 8px 并带 4px 水平内边距。
- 双层弹出菜单使用 Shadow-3、白底、6px 圆角，菜单项高 48px。

## Input 输入框

- 类型：带标签、必填、选填、无标签、带提示、带信息、带按钮、可选择图标、密码、验证码、手机、价格、数量。
- Status：active、filled、uneditable、success、warning、error。
- 布局：水平基础 56px 高；垂直基础 86px；带提示 80/110px；外置标签示例为 48px 输入框加顶部标签。
- 水平标签宽 81px，标签与输入内容间距 16px，左右内边距 16px。
- 内容文本 16/24，标签 Font Gy1，占位 Font Gy3。
- 底部分割线 Gray3 0.5px；外框输入框边框 Gray4、圆角 6px。
- 卡片式表单宽 343px、圆角 9px。
- 提示色：success `#2BA471`、warning `#E37318`、error `#D54941`。
- 后缀支持 icon、button、text、link、image。

## Picker 选择器

- 用途：从预置数据集合中选择。
- 列数：1、2、3、4；支持标题显示/隐藏。
- 弹层尺寸：375px 宽、258px 高，白底，顶部圆角 12px，底部安全区/内边距 16px。
- Header 高约 58px，标题 Title Large 18/26 Semibold 居中。
- 取消按钮左侧，Font Gy2 14/22；确认按钮右侧，Brand7 14/22。
- 选中指示条：Gray1 `#F3F3F3`，高 40px，左右 16px，圆角 6px。
- 选中项：16/24 Semibold Font Gy1；未选项：16/24 Regular Font Gy2。
- 顶部/底部使用约 48px 渐隐遮罩。

## Radio 单选

- 用途：从一组选项中选择唯一项。
- 组合方向：vertical、horizontal；选项数量 2/3/4。
- 图标位置：left/right；样式：block/card。
- 单选图标尺寸 24px；样式包括 fill-circle、dot、line/check。
- 列表项高 56px，带内容说明项高 82px；左图标与内容间距 8px，左内边距 16px。
- 分割线 Gray3 0.5px。
- 卡片样式宽 343px，纵向卡片高 82px、间距 12px；横向卡片高 56px。
- 选中卡片边框 Brand7 1.5px、圆角 6px，角标 check 标记约 28px。
- 禁用态文字使用 Font Gy4，品牌禁用使用 Brand3。

## Calendar 日历

- 类型：基础日历、带描述、双描述、区间选择、时间选择、翻页、不可选日期。
- 主要 Variant：`type=single/multiple/range`，`format=default/suffix/prefix&suffix`，`timePicker=true/false`，`switchMode=true/false`。
- 基础尺寸：375px 宽、668px 高，白底，顶部圆角 12px。
- Header：16px 内边距，标题 18/26 Semibold 居中，关闭图标 24px 右侧。
- 星期栏：左右 16px，列间距 4px，单项 14/22 Regular Font Gy2。
- 月份标题：14/22 Semibold Font Gy1；月份与表格间距 8px。
- 日期表格：7 列，每格 44x60 或等分伸缩，行/列间距 4-8px。
- 日期文字：16/24 Semibold。普通态 Font Gy1；今日 Brand7；选中白字 + Brand7 背景；范围中间 Brand1 背景；禁用 Font Gy4 或 Brand3/Error3。
- 日期单元圆角 6px；区间开始仅左侧圆角，区间结束仅右侧圆角。
- 底部确认按钮：左右 16px，按钮高 48px，Brand7 背景，6px 圆角。
- 带时间选择时，底部时间面板从日历中段覆盖上来，带顶部轻投影；时间 Picker 指示条使用 Gray1，高 40px，选中项 16/24 Semibold。

## DatetimePicker 日期时间选择器

- 用途：选择日期、月份、年份、日期周、日期时间、时、分、秒等时间点或范围。
- 模式：date、month、year、date week、date with hour/minute/second、hour、minute、second。
- 弹层尺寸：375px 宽、258px 高，白底，顶部圆角 12px。
- Header 与 Picker 一致：标题 18/26 Semibold，取消 Font Gy2，确认 Brand7。
- 指示条：Gray1 `#F3F3F3`，高 40px，左右 16px，圆角 6px。
- 选中项：16/24 Semibold Font Gy1；未选项：16/24 Regular Font Gy2。
- 列结构：date 为年/月/日，month 为年/月，date week 含星期，second 为时/分/秒，date with second 可扩展至 6 列。

## Navbar

来源：`TD_navbar`，真实节点 `1:315`「NavBar 导航栏」。用途为不同页面之间切换或者跳转，位于内容区上方、系统状态栏下方。

- 类型：MiniProgram NavBar 基础小程序导航栏、H5 NavBar 基础 H5 导航栏、NavBar with Search 带搜索导航栏、NavBar with Image 带图片导航栏。
- 基础尺寸：移动端示例宽 375px；默认高度 48px；Large 标题样式高度 104px。
- 背景：默认白色 `#FFFFFF`；自定义颜色示例使用 Brand7 `#0052D9`，标题与左侧图标切换为白色。
- 标题：默认 Title Large，18/26，Semibold，Font Gy1；支持居中与左对齐。居中标题在 375px 宽度下位于中轴，左右操作区不得挤压标题；左对齐标题起点约 44px。
- Large 标题：主标题使用 28/36 Semibold，左边距 20px；顶部返回文案使用 16/24 Regular，配合左侧 24px 返回图标。
- 左侧操作：返回图标 24px，左边距 12px；H5 可同时出现返回与关闭图标，图标间距 12px；小程序复合返回/主页胶囊高度 32px、圆角 999px，内部图标 20px。
- 右侧操作：H5 可使用主页 24px 与更多 24px，右边距 12px，图标间距 12px；小程序胶囊宽约 87px、高 32px，右边距 12px，圆角 16px，边框 Gray3 `#E8E8E8` 0.5px，内部间距约 13px。
- 搜索导航栏：搜索框位于左侧，高 32px，圆角 999px，背景 Gray1 `#F3F3F3`；左内边距 12px，搜索图标 20px，提示文本 Body Medium 14/22 Regular，Font Gy3。
- 图片导航栏：左侧图片区域示例宽 102px、高 24px，左边距 12px；右侧仍保留小程序胶囊操作。
- 分割线与边框：胶囊内部竖向分割线使用 Gray3/Gray4 0.5px；页面分组边界可使用 Gray4 `#DDDDDD` 1px。
- 交互与状态：返回、关闭、主页、更多、搜索入口均应保证不低于 32px 的可点区域；自定义深色背景下图标、标题和胶囊内容需同步反白，保持对比度。
