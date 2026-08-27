# Omarchy Community Design System

> 面向 AI 与人类设计者的品牌、界面、网站、海报、Logo、Icon 与快捷键设计规范。
>
> 版本：1.0 · 依据 Omarchy 官网、Manual、官方 `basecamp/omarchy` 仓库与社区视觉样本整理 · 2026-08-27

## 0. 使用方式

本文件是 Omarchy 社区视觉与交互语言的单一入口。开始设计前，先判断产物属于哪一层：

1. **品牌核心层**：字标、字体气质、终端语法、键盘优先、直角结构、直接文案。必须稳定延续。
2. **主题系统层**：背景、前景、强调色、状态色及壁纸。必须使用语义色角色，不把某个主题误当永久品牌色。
3. **社区表达层**：城市、聚会、文化符号、像素插画、摄影与本地色彩。允许大胆变化，但必须被前两层约束。

当规则冲突时，优先级为：**可用性与无障碍 > Omarchy 产品行为 > 品牌识别 > 单次创意表现**。

## 1. 品牌本质

Omarchy 的设计应被理解为：

> 一台高效、可塑、由键盘驱动的现代 Linux 工作站，把终端的诚实结构与个人桌面的审美自由合在一起。

### 1.1 核心气质

- **Beautiful**：不是装饰堆叠，而是主题、壁纸、终端和应用颜色形成完整环境。
- **Modern**：清晰、响应迅速、自动平铺、适配当前硬件与工作流。
- **Opinionated**：默认值明确；不把每个决定都推回给用户。
- **Keyboard-first**：界面像命令系统一样可学习、可预测、可加速。
- **Hackable**：视觉应让配置、脚本、路径和状态显得自然，而非隐藏系统本质。
- **Community-local**：社区海报可以强烈呈现城市、地标、语言和本地文化。

### 1.2 氛围量表

- 产品 UI 密度：**8/10，Cockpit Dense**。
- 官网/文档密度：**5/10，Daily App Balanced**。
- 社区海报密度：**6–9/10**，取决于插画复杂度。
- 布局变化度：**4/10**；以严格网格为基准，局部才允许偏置。
- 动效强度：**3/10**；快速、克制、服务状态变化。
- 圆润度：**1/10**；默认直角，只有小型控件、代码块和媒体允许轻微圆角。

### 1.3 一眼识别条件

一件 Omarchy 作品至少满足以下五项中的四项：

- 使用官方 Omarchy 字标或其 ASCII / 像素化逻辑。
- 以等宽字体建立主要信息层级。
- 深色终端底或严格的主题化浅色底。
- 细线边框、平铺网格、有限阴影。
- 一个明确强调色贯穿焦点、链接、选中态与关键装饰。
- 文案简短、具体、略带个性，不像企业营销模板。
- 图形包含终端、光标、像素、城市轮廓或桌面工作流中的真实元素。

## 2. 标志系统

### 2.1 官方字标

- 首选官方 `logo.svg`，不要手工重画。
- 字标来自 **Delta Corps Priest 1** 的像素/军用显示字形逻辑；官方 ASCII 字标可由 `omarchy ascii` 生成。
- 正式品牌名始终写作 **Omarchy**；字标图形内部可使用全大写造型 `OMARCHY`。
- 字标可以使用单色主题前景色、强调色或反白。不得使用多色渐变填充、描边光晕、斜切、拉伸或透视变形。
- 保持像素边缘锐利。栅格导出必须使用整数倍缩放，禁止双线性模糊。

### 2.2 安全区与最小尺寸

- 安全区以字标中单个竖向像素笔画的宽度 `x` 为单位，四周至少留 `2x`。
- 数字界面中完整字标最小宽度为 `160px`；更小时改用 Omarchy 图标或纯文字名称。
- 海报主字标可占画布宽度的 `68–90%`，但不得贴边；社区地名或活动名必须与其保留至少一个正文行高。
- 字标不得与人物、建筑、窗口边框或其他文字重叠。

### 2.3 ASCII 标志

- 终端、About、screensaver 和开发者页面优先使用官方 `logo.txt`。
- ASCII 艺术必须置于等宽环境并保留原始换行；不自动换行、不压缩字符间距。
- 自定义 ASCII 图形优先使用单列宽字符。Emoji 和双宽字符会破坏网格，不用于结构性图形。
- 从图像转换时优先清晰轮廓和高反差素材；复杂照片不直接转 ASCII。

### 2.4 图标标记

- 官方 Omarchy 私有图标字体中 `U+E900` 为 Omarchy 标记；产品界面应优先使用它或官方 SVG。
- 品牌图标必须单色，以当前主题前景或强调色着色。
- 不从字标中随意截取某个字母作为新图标；需要紧凑标记时使用官方图标。

## 3. 色彩系统

### 3.1 原则：品牌稳定，主题可变

Omarchy 没有一套覆盖所有场景的永久“品牌绿”。官网当前采用 Tokyo Night 语系，系统本身允许主题同时重染终端、窗口边框、编辑器、浏览器、Top Bar、菜单、通知、OSD 与锁屏。未来设计必须以语义角色建模。

每套主题至少定义：

```toml
mode = "dark" # 或 "light"

accent = "#7AA2F7"
selection = "#292E42"
muted = "#414868"

background = "#1A1B26"
dark_background = "#13141C"
darker_background = "#0E0E14"
lighter_background = "#24283B"

foreground = "#A9B1D6"
dark_foreground = "#565F89"
light_foreground = "#B4BEE6"
bright_foreground = "#C0CAF5"

red = "#F7768E"
yellow = "#E0AF68"
orange = "#EB927B"
green = "#9ECE6A"
cyan = "#449DAB"
blue = "#7AA2F7"
magenta = "#AD8EE6"
brown = "#75493D"
```

以上是官网与 Tokyo Night 默认语境的基准，不是所有 Omarchy 产物的强制固定色。

### 3.2 语义角色

| 角色 | 用途 | 规则 |
|---|---|---|
| `background` | 页面、窗口、菜单主底色 | 主要画布；不要叠加无意义渐变 |
| `dark_background` | 更深层、沉浸区 | 终端深层、媒体底、页脚 |
| `darker_background` | 最深层 | 遮罩、边缘、极低层背景 |
| `lighter_background` | 提升表面 | 代码块、列表悬停、二级面板 |
| `foreground` | 正文与常规 UI | 必须达到可读对比度 |
| `bright_foreground` | 标题、输入光标 | 最高文字层级，不滥用 |
| `dark_foreground` | 次级信息 | 占位符、注释、失活项 |
| `accent` | 焦点、链接、当前项 | 单屏主要强调色只用这一种 |
| `selection` | 文本与列表选中背景 | 与 `bright_foreground` 配对 |
| `muted` | 分隔线、注释、轨道 | 不用于关键正文 |
| `red` | 错误、危险、录制、警报 | 不把品牌强调误当错误色 |
| 其余 ANSI 色 | 图表、代码、状态 | 有语义才使用，避免彩虹化 |

### 3.3 官网基准色

当产物需要“官方官网感”且没有指定主题时，使用：

- **Night Canvas** `#1A1B26`：页面主背景。
- **Storm Surface** `#24283B`：代码块和提升表面。
- **Terminal Blue** `#7AA2F7`：按钮、链接和主要强调。
- **Terminal White** `#C0CAF5`：正文和高对比文字。
- **Omarchy Green** `#9ECE6A`：ASCII 字标、序号、列表标记。
- **Terminal Cyan** `#7DCFFF`：链接悬停前的鲜明信息色；系统主题文件中的 cyan 可较暗，官网展示色以此为准。
- **Muted Terminal** `#414868`：边框、注释和低层信息。
- **Pure White** `#FFFFFF`：只用于最高级标题或 hover 峰值，不作大面积底色。

### 3.4 社区海报用色

- 每张海报选一个母主题：黑绿终端、Tokyo Night 蓝、夕阳洋红橙、地区旗帜色或当地夜景色。
- 使用 **1 个主强调色 + 最多 2 个辅助状态色**。大面积图像可丰富，但文字与框架仍受此限制。
- 黑绿海报不是唯一答案。Berlin、Hamburg、Warsaw、Leiden 样本证明单色像素线稿有效；Dubai、Brno、Seoul 样本证明主题化摄影/插画同样有效。
- 国旗仅作为明确地区语境中的内容，不把旗帜颜色强行扩散到所有 UI。
- 可使用局部像素抖动、扫描线与颗粒；不要加模糊霓虹外发光。

### 3.5 对比与状态

- 正文与背景至少达到 WCAG AA；小字号与快捷键提示优先达到 `4.5:1`。
- 焦点不能只靠颜色：同时使用边框、底色、光标或字重变化。
- 错误、警告、成功分别优先使用 `red`、`yellow/orange`、`green`，并配合文字或图标。
- 浅色主题必须整体反转层级，不能只把背景换白；参考 Flexoki Light 的暖白 `#FFFCF0` 与深墨 `#100F0F`。

## 4. 字体系统

### 4.1 字体家族

- **产品 UI、官网、文档、正文、数字、快捷键**：`JetBrains Mono`。
- **Linux 桌面实际环境**：`JetBrainsMono Nerd Font`，以保证 Nerd Font 图标正常显示。
- **字标**：官方 SVG / ASCII；需要生成同类文字时使用 Delta Corps Priest 1，不把它当正文。
- **品牌图标**：官方 `omarchy` 私有图标字体，只用于已定义的品牌 glyph。
- 回退：`"JetBrains Mono", "JetBrainsMono Nerd Font", ui-monospace, monospace`。

不要用 Inter、通用无衬线或衬线字体把 Omarchy“企业化”。中文必须选一套等宽或视觉上稳定的 CJK 回退，并与西文基线对齐；推荐在具体平台测试 `Noto Sans Mono CJK SC` / `Sarasa Mono SC`，不要假设中英文等宽自动成立。

### 4.2 产品 UI 字阶

以 `12px` 为 shell 基准：

| Token | 尺寸 | 用途 |
|---|---:|---|
| `caption` | `10px` | 极短元数据、辅助提示 |
| `body-small` | `11px` | 稠密列表次级信息 |
| `body` | `12px` | 默认 UI 文本 |
| `subtitle` | `13px` | 分组副标题 |
| `title` | `14px` | 面板标题、按钮强调 |
| `heading` | `16px` | 页面/对话框标题 |
| `display` | `24px` | 状态数字、重要结果 |
| `display-large` | `28px` | 大型状态或品牌辅助标题 |

- 网站正文建议 `clamp(13px, 1.25vw, 16px)`，行高 `1.4–1.5`，每行不超过 `68ch`。
- 标题通过字重、颜色和留白建立层级，不依赖巨大字号。
- 数字、日期、温度、进度和系统状态使用等宽数字，保持列对齐。

### 4.3 字重与大小写

- 正文 `300–400`；链接、标题、按钮 `700`；避免中间层级过多。
- 产品菜单使用自然的 Title/Sentence Case：`File manager`、`Default Browser`、`With desktop audio`。
- 网站按钮可全大写，配合紧凑、短标签：`MANUAL`、`ISO`、`GITHUB`。
- 海报中 `OMARCHY` 可全大写；城市名、日期和活动名可全大写，但正文不全大写。
- 不通过超宽字距伪造“未来感”。只在短地名、元数据或像素副标题中使用受控 tracking。

## 5. 图像与插画

### 5.1 社区海报构图

推荐 1:1 主画布，结构从上到下为：

1. Omarchy 字标，宽度约画布的 `70–88%`。
2. 地名/活动名/年份，建立第二层识别。
3. 城市地标、社区场景或主题图形，占主要叙事面积。
4. 日期、地点、开放性、主办方等事实信息。

允许三种视觉模式：

- **像素线稿**：黑底，单色或双色地标天际线，镜像水面、点阵与小型终端符号。
- **主题化插画**：像素/复古未来主义，高对比日落、夜城、道路、车辆、地区自然景观。
- **真实场景 + 像素排版**：低曝光摄影或插画化照片，上层使用官方字标和等宽信息。

### 5.2 内容准则

- 地标要可识别且与当地真实相关；不要生成“泛城市天际线”。
- 人物用于表达社区时，应呈现协作、电脑、聚会的真实情景，避免无意义商务握手。
- Linux/Tux 可作为社区文化符号，但不是每张图都必须出现。
- Arch、Hyprland 或合作方标志必须使用各自官方资产，并保持从属层级。
- 对汽车、建筑、国旗、赞助商标志进行事实核验；不凭空拼接不存在的细节。

### 5.3 质感

- 像素图：硬边、有限调色板、整数像素、受控抖动。
- 摄影：夜景、低照度、屏幕光、真实工作环境；保留暗部，不做 HDR 糖果色。
- 复古未来主义：允许扫描线、CRT 颗粒、点阵、低分辨率日落；禁止泛滥的紫蓝 AI 霓虹和无来源电路线。
- 任何纹理都不得降低文字对比；必要时用纯色 scrim，而非发光描边补救。

### 5.4 扩展视觉方言

社区应用不必都伪装成系统设置面板。新增样本显示以下方言与 Omarchy 核心兼容：

- **复古印刷/广告**：旧纸张、网点、褪色油墨、70–90 年代广告排版和带态度的标语。可使用不同展示字体，但系统窗口、数据和控件仍回到等宽字体。
- **高饱和主题桌面**：壁纸可以大胆、电影化或 synthwave；浮层必须用足够不透明的主题表面与清楚边框维持可读性。
- **Playful utility**：宠物、游戏化状态和像素动画可以幽默；进度、动作与错误仍要准确，不以可爱感掩盖系统状态。
- **Single-purpose panel**：汽车、火箭、耳机、AI 配额等面板可围绕真实对象建立领域化信息架构，但保持终端式标签、数字对齐和快速操作。

当作品使用非官方字样、复古字体或实验性 Logo 时，必须标注为活动/社区创意，不能替代官方品牌资产。

## 6. Icon 设计

- 优先使用 Nerd Font 或简洁单色 SVG，确保与文字同色、同基线。
- 图标采用 `24 × 24` 或 `32 × 32` 设计网格，主笔画视觉重量一致。
- 轮廓图标建议 `1.5–2px` 笔画；像素图标必须落在整数网格。
- 默认无容器、无渐变、无阴影；只有应用图标需要独立底板。
- 菜单行图标置于固定宽度列，不能因 glyph 宽度变化导致标签抖动。
- 品牌标记一律单色；选中时改为 `accent`，而非叠加发光。
- 不用 Emoji 替代功能图标。Emoji 可作为内容输入，不作为系统导航语言。

### 6.1 品牌 Glyph 来源

- 第一选择是品牌官方发布的平面单色标记；只有官方没有合格素材时，才使用 [Simple Icons](https://simpleicons.org/) 等图标集的单色重绘。
- 输入必须是单色 SVG，且只有一个 `<path>`。菜单会用当前主题的 foreground 与 selection 重新着色，原始颜色不会保留。
- 不直接使用普通 App favicon：它们经常是多色、带容器底板或由多个 path 组成，不适合字体 glyph。
- 两色 Logo 是高风险来源。转成字体后所有 path 都会变成同一实色；若标记依赖深浅两半表达意义，结果会成为不可读色块。
- 以“只看纯色 silhouette 是否仍能一眼识别”为验收标准；细内部纹理、文字和负空间过小的标记应另找来源。
- 在 README 记录每个 glyph 的品牌、来源 URL、私有区码点和必要说明，确保后续可审计。

### 6.2 官方字体工作流

不要手工编辑 `omarchy.ttf`。在官方仓库中使用：

```bash
omarchy dev font list
omarchy dev font add ollama https://simpleicons.org/icons/ollama.svg
```

`add` 会抓取 SVG，将图形缩放到现有标记共用的 `64..960` 坐标盒以匹配视觉尺寸，追加到下一个可用的 Private Use Area 码点，并更新字体 README。命令会输出码点与 glyph，交付前必须在菜单正常态和选中态各检查一次。

## 7. UI 设计语言

### 7.1 网格与空间

- 优先 CSS Grid / 明确平铺区域。界面应像可读的窗口管理布局，而不是漂浮卡片集合。
- 基础空间序列：`2, 3, 4, 6, 8, 10, 12, 14, 18px`；大页面可扩展到 `24, 32, 48, 64px`。
- Shell 基准：窗口内边距紧凑，外间距大于内间距。官方 Hyprland 默认 `gaps_in: 5px`、`gaps_out: 10px`、边框 `2px`。
- Web 内容最大宽度按任务决定：阅读区 `50em` 左右；复杂工作台不超过 `1600px` 且保留外边距。
- 移动端 `<768px` 单列折叠；不得出现页面级横向滚动。代码和表格可以在局部容器滚动。

### 7.2 几何

- 系统窗口默认 `0px` 圆角、无窗口阴影、无模糊。
- 按钮与搜索结果容器允许 `0.3–0.5em` 的轻微圆角；不要使用胶囊按钮。
- 主要结构靠 `1–2px` 边框和间距分组，不靠大面积阴影。
- 边框使用 `muted`、前景低透明度或当前活动边框色；当前窗口/焦点必须清楚。
- 渐变仅在主题明确配置活动边框时使用，不能自行添加“品牌渐变”。

### 7.3 表面层级

- 页面底：`background`。
- 提升面：`lighter_background` 或前景 `4–8%` 透明填充。
- Hover / 键盘光标：前景 `8%` 填充 + `25%` 边框。
- Focus：与 Hover 同一视觉语法，避免鼠标和键盘形成两套系统。
- Selected：前景 `18%` 填充；必要时文字变 `accent`。
- Pressed：前景 `22%` 填充并产生轻微按压位移。
- 全屏菜单 scrim：使用 `background` 约 `50%` 透明度。

### 7.4 按钮

- 主按钮：`accent` 实底、深色文字、粗体、短标签；单个区域通常只设一个主按钮。
- 次按钮：透明底 + `1px` 低对比边框，或纯文字链接。
- 高度：产品 UI 最低 `28px`，触屏 Web 最低点击区域 `44px`。
- 图标与标签间距约 `1ch`；图标不重复标签含义时才使用。
- Hover 只改变背景/文字/边框，不做放大、旋转或发光。
- Active 可 `translateY(1px)`；disabled 保留在列表中、降低对比，并可用 `✓` 表示已经安装/已满足。

### 7.5 菜单与列表

- 菜单是命令树，不是营销导航。每行是一个名词目的地或一个清晰动作。
- 固定图标列 + 标签列 + 可选快捷键/状态列。
- 行高默认 `28px`，稠密但可扫描；指针和键盘光标共享选中态。
- 子菜单标题可以比入口标签更具体，如入口 `Browser`，页标题 `Default Browser`。
- 当前选择使用 `✓`；不可用但已安装的项保持可见并变暗，未安装的 Remove 项可隐藏。
- 搜索匹配标签、稳定 ID 的末段和描述；不要为新条目随意添加 alias。

### 7.6 输入与表单

- 标签在输入框上方；帮助文字在下方；错误紧邻字段。
- 搜索框可采用“安静的底线”样式：透明背景、仅底部 `1px` 边框，聚焦改为强调色。
- 配置确认适合终端表格：`Field | Value`，最后用明确问题 `Does this look right?`。
- 默认选项使用实色条标出，并提供可直接按下的字符提示，如 `y Yes`、`n No`。
- 密码、删除、磁盘格式化等高风险动作必须清楚说明后果，不用幽默掩盖风险。

### 7.7 通知、OSD 与状态面板

- 通知/OSD 使用主题背景、前景文字和活动窗口同源边框。
- 信息结构：图标/关键数字 → 简短标题 → 必要的单行补充。
- 时间、日期、电池示例采用自然句：`Friday 12:10 · 14 August 2026 · Week 33`。
- 天气、电池等丰富面板允许大数字，但仍保持一条细边框、无阴影、无磨砂玻璃。
- 状态变化在原位更新；不要每次刷新都弹新卡片。

### 7.8 代码、表格和技术内容

- 行内代码用 `lighter_background` / `muted` 半透明底与 cyan/accent 文字。
- 代码块圆角最多 `0.5em`，不加模拟 macOS 红黄绿窗口点。
- 表格使用 `1px` 低对比边框、左对齐、紧凑单元格；数字列右对齐。
- 列表 marker、章节序号和锚点可用 green 或 accent，形成终端索引感。
- 长日志和系统指标优先对齐成列，所有数字使用等宽字体。

### 7.9 空状态、加载与错误

- 空状态说明“这里是什么”与“下一步按什么”，不要只写 `No data`。
- 加载使用与真实布局同尺寸的低对比骨架或单行终端进度，不用大型圆形 spinner。
- 错误直接说明失败对象、原因和恢复动作；技术用户可展开命令或日志。
- 成功反馈短促，如 `Theme applied`、`Copied`、`Installed`，完成后自动消退。

### 7.10 数据面板与领域 Widget

- 面板顶部采用“对象图标 + 对象名 + 短状态/副标题”，右侧可放一个关键值。
- 信息按任务分组，用细分隔线而不是嵌套卡片：概要 → 进度 → 详情 → 操作。
- 标签用低对比前景，值用正常或明亮前景；单位紧跟数值并保持等宽对齐。
- Progress track 使用 muted 表面，fill 使用前景或 accent；危险阈值才切换到状态色。
- 二元开关、模式选择和当前项必须同时有位置、底色或 `✓`，不能只变文字颜色。
- 底部操作最多保留 2–3 个同级按钮；主要动作实底或选中填充，其余 outline。
- 面板可悬浮在强烈壁纸上，但 scrim/表面必须足够实，背景图不得穿透到正文造成噪声。

### 7.11 插件目录与资源市场

- 插件浏览属于“可比较集合”，允许规则化卡片网格；这不是营销页的三等分功能卡。
- 每张卡的固定顺序：预览图 → 名称与可信度/热度 → 作者与类型 → 一句具体说明 → 标签与安装方式。
- 保持卡片高度、元数据位置和操作位置一致，便于横向扫描；文字过长截断并提供详情页。
- Verified/Unverified、Updated、Manual setup 等属于风险和维护状态，必须高对比且用文字表达，不能只靠颜色。
- 点赞、收藏、浏览、复制等计数使用单色 icon + 等宽数字；不要让社交指标压过插件用途。
- 网格响应式为大屏 3 列、中屏 2 列、小屏 1 列。卡片边框 `1px`、方角、无浮夸 hover elevation。
- 搜索、类别、验证状态、安装方式应可键盘筛选；Card 本身与内部操作必须有明确焦点顺序。

### 7.12 高密度桌面应用

- 邮件、音乐、文件与管理工具可以使用经典 master-detail：导航侧栏 → 列表/集合 → 详情；不要把每条内容都装进独立浮卡。
- 宽屏优先三栏，窄窗口降为“顶部模式/分类条 + 单列表”，打开项目后进入单详情页并提供明显 `← Back`。
- 底部可保留常驻状态/快捷键 rail，例如 `j / k move`、`Enter open`、`e archive`；提示必须反映当前上下文，而非展示整套快捷键百科。
- 列表项结构固定：主标题、次摘要、时间/状态、行内动作。Hover 与键盘 cursor 使用同一底色；只在 cursor 行显示低频动作可降低噪声。
- 媒体应用允许专辑封面等真实内容提供色彩，应用 chrome 仍保持主题前景、边框和等宽排版。
- 空详情区可同时承担 onboarding：对象图标、当前集合名、项目数量与 3–6 条最关键的键盘操作。
- 搜索框始终处于清楚的全局或当前范围；范围选择写成具体状态，如 `In Red Hot Chili Peppers`，避免模糊筛选。

### 7.13 Shell 组件状态模型

- 一个面板同一时刻只显示一个键盘 cursor。面板根维护 `focusSection + selectedIndex`，鼠标进入时更新同一状态模型，不创建第二个 hover 高亮。
- 初次打开可不高亮任何行；用户第一次按方向键或移动鼠标后再出现唯一 cursor。
- 状态优先级固定为：`pressed > activeFocus > hover/cursor > selected/active > idle`。
- `selected` 表示持久选择，`cursor` 表示瞬时导航目标，`activeFocus` 表示正在接收文本/控件输入；三者不能混为一种状态。
- 控件必须预留其最大边框宽度，避免 hover/focus 出现时尺寸变化并推动相邻元素。
- Tooltip 延迟约 `400ms`，只解释不自明的图标或动作；键盘焦点也应能获得等价说明。
- 分区标题使用小号、粗体、低亮度的 terminal small-caps 气质；分隔线为前景色约 `12%` 的 `1px` hairline。

## 8. 网站设计

- 页面顺序优先：ASCII/官方字标 → 一句价值主张 → 核心入口 → 真实产品演示/内容。
- 首页可居中呈现字标，但内容页与工具页以左对齐和清晰网格为主。
- 导航按钮数量多时允许自然换行；保持等距，不把最后一个按钮孤立成不平衡布局。
- 链接默认强调色并保留下划线；Hover 提升到高亮前景。
- 文档侧栏使用带前导零的章节号、低对比默认项、高对比当前项。
- 内容标题只比正文大 `1.1–1.75×`；技术文档不使用巨型营销标题。
- 正文图片可有 `0.5em` 圆角；海报、像素图和 Logo 不因全局样式被强制圆角。
- 桌面端侧栏可 sticky；移动端隐藏侧栏，保留搜索和章节导航入口。

## 9. 动效与反馈

- 默认过渡：`150ms cubic-bezier(0.33, 1, 0.68, 1)`。
- 窗口进入可采用快速 `popin`，目标比例约 `87% → 100%`；退出更快。
- 只动画 `transform` 与 `opacity`；不为装饰持续占用 CPU。
- 允许的品牌微动效：ASCII 标志每隔数秒掠过一次短暂绿色 glint，随后完全静止。
- 列表无需瀑布式逐项动画；键盘操作必须立即响应。
- 尊重 `prefers-reduced-motion`，并确保关闭动画后信息完整。
- 禁止弹跳箭头、无限浮动卡片、呼吸光环、视差堆叠和自定义鼠标光标。

## 10. 文案风格

### 10.1 语气

- **直接**：说清楚动作与结果。
- **具体**：写 `Open file manager in terminal's current directory`，不要写 `Boost your workflow`。
- **有主见但不傲慢**：可以推荐默认值，也要明确如何更改。
- **技术上诚实**：路径、快捷键、风险和限制都可以直接出现。
- **轻微个人感**：文档允许自然口语和一点幽默，但错误、安全和破坏性操作保持严肃。

### 10.2 微文案规则

- 菜单标签使用短名词或动词：`Apps`、`Style`、`Install`、`Lock`、`Share`。
- 启动入口用对象名：`Terminal`、`Browser`、`File manager`。
- 切换操作用 `Toggle + 对象`；设置默认项用 `Default + 对象`。
- 进行中使用现在分词：`Installing…`；完成使用过去式：`Installed`。
- 危险动作明确宾语：`Reset Computer`、`Erase disk`，不要只写 `Continue`。
- 避免：`Elevate`、`Unleash`、`Seamless`、`Next-gen`、`Supercharge`、`Reimagine`。
- 不用 Emoji 作为 UI 语气；Nerd Font 图标属于界面语法，不属于文案。

### 10.3 标点与数字

- 英文界面使用 Sentence case；菜单不以句号结尾。
- 描述句使用完整标点；终端输出可省略句号。
- 快捷键使用 `Super + Shift + F`，运算符两侧保留空格。
- 路径、命令、键名使用反引号；界面路径用 `Style > Font`。
- 时间和日期必须符合目标地区习惯；同一界面不要混用 `12:10 PM` 与 `12:10`。

## 11. 命名规范

### 11.1 用户可见名称

- 品牌：`Omarchy`，不写 `OMarchy`、`O'Marchy` 或 `Omarchy OS`，除非上下文需要说明系统类别。
- 功能名优先具体对象：`Theme`、`Background`、`Font`、`Screenrecord`。
- 同级菜单保持平行词性，不混用宣传短语。
- 官方产品名保留原拼写：`Hyprland`、`Neovim`、`GitHub`、`ChatGPT`、`OpenCode`。

### 11.2 菜单 ID

- 使用小写 `kebab-case` 和点分层级：`trigger.capture.screenshot`、`setup.default.browser`。
- ID 反映导航树；不要另设重复的 `parent`。
- 已发布 ID 视为稳定接口。重命名必须考虑 CLI route 与用户脚本兼容。
- `aliases` 只保留已有常用名称，不作为新条目的搜索关键词垃圾桶。

### 11.3 命令与文件

- 所有用户命令以 `omarchy-` 开头。
- 目的前缀：`launch-`、`install-`、`setup-`、`toggle-`、`theme-`、`update-`、`capture-`、`restart-`、`refresh-`、`pkg-`、`hw-`。
- CLI 面向用户时使用分组形式：`omarchy theme set <name>`。
- 社区主题仓库推荐命名：`omarchy-[theme-name]-theme`。
- 主题目录与技术 ID 用小写 kebab-case；展示名可用自然 Title Case。
- 图片按用途与地点命名：`meetup-seoul-2026-square.webp`，不要使用 `final-final-2.png`。

### 11.4 插件命名

- 官方插件 ID 使用保留命名空间 `omarchy.*`，例如 `omarchy.clock`、`omarchy.network`。
- 第三方插件必须使用作者或组织命名空间，如 `alice.weather`；不得冒用 `omarchy.*`。
- Manifest 的 `id` 是稳定机器标识，`name` 是人类可读名称；不要把版本号塞进两者。
- 一个插件可声明 `bar-widget`、`panel`、`overlay`、`menu`、`service`、`bar` 等 kind；名称和预览必须真实反映它提供的入口。
- 克隆官方插件进行个性化时采用 `<username>.<plugin>`，展示名可用 `My Clock` 这类清楚的个人副本名称。

## 12. 快捷键设计

### 12.1 修饰键语法

Omarchy 的快捷键不是随机组合，而是一套层级：

| 模式 | 含义 | 示例 |
|---|---|---|
| `Super + key` | 核心导航、窗口动作 | `Super + Space` 菜单，`Super + F` 全屏 |
| `Super + Shift + key` | 启动主要应用 | `Super + Shift + F` 文件管理器 |
| `Super + Ctrl + key` | 系统工具、面板、直接控制 | `Super + Ctrl + T` Activity |
| `Super + Alt + key` | 替代版本或次级入口 | `Super + Alt + Return` Tmux |
| 增加 `Shift/Alt/Ctrl` | 同一动作族的变体 | 私密浏览、前一项、全部清除 |

### 12.2 分配规则

- 新快捷键先选择语义字母：`B` browser、`F` files、`T` terminal/activity、`K` keybindings。
- 同一家族沿用同一主键，通过修饰键表达变体，不换成无关字母。
- `Super + Shift` 保留给应用启动；`Super + Ctrl` 优先系统控制；`Super + Alt` 优先替代模式。
- 全局快捷键必须能在 `Super + K` 的 Keybindings 中发现。
- 重新绑定前先检查冲突；覆盖已有绑定时先 unbind，并告诉用户原动作。
- 不用四个修饰键完成高频操作；复杂组合只留给低频、危险或高级变体。
- 键盘、鼠标和触控路径应触发相同状态与结果；键盘不是二等入口。

### 12.3 快捷键展示组件

- 视觉格式：每个键独立 keycap，`+` 作为普通分隔符；或在高密度列表中直接写 `Super + Shift + F`。
- Keycap 使用 `1px` 边框、主题背景、等宽粗体，无 3D 塑料质感。
- 按实际输入顺序排列修饰键：`Super` → `Ctrl` → `Shift` → `Alt` → 主键；已有官方组合可保持源码顺序。
- 使用键名 `Return`、`Escape`、`Backspace`、`Print`、`Arrow Left`，不要在同一页面混用 `Enter/Return`。
- 表格中快捷键列不换行；移动端可让功能描述换行到下一行。

### 12.4 面板内导航

- 列表/网格面板默认同时支持方向键与 Vim 键：`j/k` 上下，`h/l` 左右。
- `Return` / `Enter` 激活主动作，`Space` 激活或切换当前控件，`Escape` 关闭面板。
- `Tab` / `Shift + Tab` 在语义 section 之间移动，而不是逐个穿过几十个只读标签。
- `x` 只用于上下文中明确可理解的删除/移除，并应在 footer hint 中出现；高风险删除仍需确认。
- 进入文本框时暂时阻断面板级快捷键，让输入法和编辑键优先；退出输入后恢复面板导航。
- Footer hint 的推荐格式为 `↑↓/jk row · ←→/hl adjust · Tab section · Backspace reset · Esc close`，只列当前可用动作。

## 13. 响应式与无障碍

- 所有主要操作可用键盘完成，焦点顺序与视觉顺序一致。
- `:focus-visible` 必须清楚，使用强调色或活动边框，不移除 outline 后无替代。
- 触控目标至少 `44 × 44px`；稠密桌面 shell 可为 `28px` 行高，但需完整键盘支持。
- 图标按钮必须有可访问名称；装饰性 ASCII/SVG 对辅助技术隐藏，并提供文本品牌名。
- 页面缩放到 `200%` 仍可操作；正文不低于 `13px`，Web 主正文建议不低于 `16px`。
- 不以颜色作为唯一信息载体；状态添加图标、文字或 `✓`。
- 像素字体只用于字标和短标题，不用于长正文或关键说明。
- 亮色/暗色主题都单独检查对比、图片 scrim 和代码高亮。

## 14. 禁止项

- 不把 Omarchy 简化成“黑底 + 荧光绿 + 黑客兜帽人”。
- 不用通用 SaaS 蓝紫渐变、玻璃拟态、发光圆角卡片。
- 不用三张等宽“卖点卡”作为营销页默认结构；插件市场等真实可比较集合允许规则卡片网格。
- 不使用巨型无衬线营销标题替代官方字标。
- 不把像素字用于长正文。
- 不给所有容器加圆角和阴影。
- 不在深色主题上堆叠低对比灰字。
- 不用 Emoji 代替功能 icon。
- 不使用假的终端内容、随机十六进制、无意义代码雨。
- 不生成与地点无关或事实错误的地标。
- 不让装饰穿过文字、按钮或可点击区域。
- 不隐藏危险操作的真实后果。
- 不发明与官方现有快捷键冲突的新组合。
- 不将某个具体主题色硬编码成跨主题组件的永久颜色。

## 15. AI 生成检查清单

生成前：

- [ ] 已明确产物是品牌核心、产品主题还是社区表达。
- [ ] 已指定目标主题和 `mode`，或采用官网 Tokyo Night 基准。
- [ ] 已拿到官方 Logo / Icon，而不是凭记忆重画。
- [ ] 已核对地名、日期、地标、赞助商和快捷键。

生成中：

- [ ] 使用 JetBrains Mono / Nerd Font 语法与正确字标。
- [ ] 只用一个主要强调色，状态色有明确含义。
- [ ] 网格、边框和间距承担结构，阴影与圆角保持克制。
- [ ] 文案短、具体、可执行，没有 AI 营销套话。
- [ ] Hover、Focus、Selected、Pressed、Disabled 都有状态。
- [ ] 桌面与移动布局均可用，键盘路径完整。

交付前：

- [ ] 在 `1×` 与 `2×` 检查像素边缘和 Logo 清晰度。
- [ ] 检查 WCAG 对比、键盘焦点、缩放和减少动态效果。
- [ ] 检查深色与浅色主题，不存在固定颜色泄漏。
- [ ] 对照官方 Keybindings 检查冲突。
- [ ] 删除无意义 glow、gradient、glass、营销卡片和装饰代码；保留有比较或层级作用的面板。

## 16. 可直接复用的 AI 设计指令

```text
Design this as part of the Omarchy community system.

Preserve the brand core: official sharp pixel/ASCII Omarchy wordmark, JetBrains Mono typography, terminal-native information structure, keyboard-first interaction, dense grid-based layout, thin borders, square geometry, restrained motion, and concise opinionated copy.

Treat color as a theme, not a fixed brand palette. Use semantic roles for background, darker/lighter surfaces, foreground levels, accent, selection, muted, and ANSI status colors. Use one primary accent per screen. Default to the official website's Tokyo Night palette only when no theme is specified.

For community artwork, ground the image in the real local city or culture. Choose pixel-line skyline, themed retro-futurist illustration, or authentic low-light community photography. Keep the official wordmark dominant and crisp. Avoid generic cyberpunk, neon glow, glassmorphism, pill-shaped UI, SaaS card grids, fake terminal noise, emojis as UI icons, and AI marketing copy.

Every interaction must define keyboard behavior and visible hover, focus, selected, pressed, disabled, loading, empty, success, and error states. Validate responsive layout, contrast, reduced motion, factual place details, and shortcut conflicts before delivery.
```

## 17. 依据与来源

本规范从以下一手资料提炼，具体实现发生变化时以官方源码与 Manual 为准：

- [Omarchy 官网](https://omarchy.org/)：官网配色、JetBrains Mono、ASCII 字标、按钮与页面结构。
- [Omarchy Manual](https://omarchy.org/manual/)：产品语气、导航、安装、主题、字体、背景与使用模型。
- [Hotkeys](https://omarchy.org/manual/hotkeys/)：官方快捷键体系。
- [Navigation](https://omarchy.org/manual/navigation/)：键盘优先与 Hyprland 平铺交互。
- [Fonts](https://omarchy.org/manual/fonts/)：默认 JetBrainsMono Nerd Font 与可替换字体。
- [Branding](https://omarchy.org/manual/branding/)：Logo、ASCII、screensaver、About 与 Delta Corps Priest 1。
- [Making your own theme](https://omarchy.org/manual/making-your-own-theme/)：主题结构、跨应用颜色同步与仓库命名。
- [Omarchy CLI](https://omarchy.org/manual/omarchy-cli/)：命令与菜单路径模型。
- [Shell Plugins](https://omarchy.org/manual/shell-plugins/)：插件类型、命名空间、安装安全与用户可扩展模型。
- [官方源码仓库](https://github.com/basecamp/omarchy)：`logo.svg`、`logo.txt`、主题、Hyprland、Shell、菜单与图标字体。
- [Theming reference](https://github.com/basecamp/omarchy/blob/quattro/docs/theming.md)：`colors.toml` 语义色、Shell 控件状态与主题渲染。
- [Menu reference](https://github.com/basecamp/omarchy/blob/quattro/docs/menu.md)：菜单 ID、Provider、Guard、Selected/Disabled 行为。
- [Shell reference](https://github.com/basecamp/omarchy/blob/quattro/docs/omarchy-shell.md)：字体比例、间距、Bar 尺寸与 Shell token。
- [官方 GitHub 仓库](https://github.com/basecamp/omarchy) 中的 `shell/Commons/Style.qml`、`shell/Ui/Button.qml`、`shell/Ui/PanelKeyCatcher.qml` 与 `agents/skills/visual-verification.md`：用于核对状态优先级、单 cursor、Vim 导航、Tooltip 与视觉验收要求。
- [Official logo.svg](https://github.com/basecamp/omarchy/blob/quattro/logo.svg) 与 [logo.txt](https://github.com/basecamp/omarchy/blob/quattro/logo.txt)：正式字标资产。
- [Official theme palettes](https://github.com/basecamp/omarchy/tree/quattro/themes)：Tokyo Night、Gruvbox、Catppuccin、Kanagawa、Osaka Jade、Flexoki Light 等。
- 用户提供的官方/社区样本：城市海报、安装器、字标、Top Bar、通知、天气、插件市场、领域 Widget、高密度应用和多主题桌面。
