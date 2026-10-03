<!--
  ========================================================================
  Markdown 语法参考手册
  说明：本文件用于演示 MkDocs (Material 主题) 下的常用 Markdown 语法。
   提供详细的编写说明，
  同时在正文中给出渲染后的实际效果，方便对照学习。
  ========================================================================
-->
文中以 HTML 注释的形式给出每个语法的说明，便于在 Markdown 编辑器中查看。请注意，HTML 注释不会在渲染后的页面（该页面）中显示。
# Markdown 语法参考手册

<!--
  一级标题用一个 # 号表示。在 MkDocs 中，一级标题通常作为页面标题。
  注意：一个页面最好只出现一个一级标题。
-->

本页汇总了在 MkDocs（Material 主题）环境下常用的 Markdown 语法，涵盖文本格式、颜色、对齐、链接、媒体、表格、代码等常见场景。文中每个示例都配有注释，可直接复制到自己的文档中使用。

---

<!-- 分隔线：三个以上的短横线、星号或下划线单独占一行即可生成分隔线 -->

## 一、标题（Headings）

<!--
  Markdown 支持六级标题，分别用 1~6 个 # 号表示，# 号与文字之间需有一个空格。
  标题会自动生成锚点，可用于页面内跳转（见后文"链接"章节）。
-->

# 一级标题（H1）
## 二级标题（H2）
### 三级标题（H3）
#### 四级标题（H4）
##### 五级标题（H5）
###### 六级标题（H6）

> **注释：** 实际编写时，同一页面通常只保留一个 `#`（即页面标题），其余使用 `##` 及以下层级，以保持结构清晰。<br>在 MkDocs 中，从`##` 级别的标题开始会显示在页面右侧的目录中，便于快速跳转。但由于本例为了演示所有标题级别，有多个一级标题，因此导致目录出现故障

---

## 二、段落与换行

<!--
  段落：连续的文字即为一个段落，段落之间用空行分隔。
  换行：在一行末尾添加两个以上空格然后回车，可实现"软换行"（不另起段落）。
  也可以使用 HTML 的 <br> 标签强制换行。
-->

这是第一个段落。段落之间需要空行才能分开。

这是第二个段落。第一行末尾加两个空格  
即可在同一段落内换行。

也可以使用 `<br>` 标签换行：第一行<br>第二行<br>第三行。

---

## 三、文本格式（加粗、倾斜、删除线、行内代码）

<!--
  加粗：**文字** 或 __文字__
  倾斜：*文字* 或 _文字_
  加粗+倾斜：***文字*** 或 ___文字___
  删除线：~~文字~~（部分标准 Markdown 不支持，但 Material 主题支持）
  行内代码：`代码`
-->

- **这是加粗文本**（使用 `**` 包裹）
- *这是倾斜文本*（使用 `*` 包裹）
- ***这是加粗并倾斜的文本***（使用 `***` 包裹）
- ~~这是删除线文本~~（使用 `~~` 包裹）
- `这是行内代码`（使用反引号包裹）
- 可以**混合**使用，例如：**加粗中包含*倾斜***

---

## 四、颜色（文字颜色、背景色）

<!--
  标准 Markdown 不支持颜色，需借助 HTML 标签 + 内联样式实现。
  文字颜色：<span style="color:颜色值;">文字</span>
  背景色：<span style="background-color:颜色值;">文字</span>
  颜色值可用：颜色名（red）、十六进制（#ff0000）、RGB（rgb(255,0,0)）等。
-->

### 4.1 文字颜色

<span style="color:red;">红色文字</span>
<span style="color:green;">绿色文字</span>
<span style="color:blue;">蓝色文字</span>
<span style="color:#ff8800;">橙色文字（十六进制）</span>
<span style="color:rgb(128,0,128);">紫色文字（RGB）</span>

### 4.2 背景色

<span style="background-color:yellow;">黄色背景</span>
<span style="background-color:#ffe4e1; color:#8b0000;">浅粉底 + 深红字</span>
<span style="background-color:black; color:white;">黑底白字</span>

### 4.3 组合使用

<span style="color:#fff; background:linear-gradient(90deg,#ff6b6b,#4ecdc4); padding:2px 8px; border-radius:4px;">渐变背景标签</span>

---

## 五、字体与字号

<!--
  字体：通过 font-family 指定，需用户系统已安装该字体才生效。
  字号：通过 font-size 指定，单位可用 px、em、rem、% 等。
  也可组合 font-weight（粗细）、font-style（样式）等属性。
-->

### 5.1 字体

<span style="font-family:'Microsoft YaHei';">微软雅黑字体</span>
<span style="font-family:'SimSun';">宋体字体</span>
<span style="font-family:'KaiTi';">楷体字体</span>
<span style="font-family:'Courier New';">Courier New 等宽字体</span>

### 5.2 字号

<span style="font-size:12px;">12px 小字号</span>
<span style="font-size:16px;">16px 正常</span>
<span style="font-size:24px;">24px 较大</span>
<span style="font-size:2em;">2em 相对单位</span>
<span style="font-size:150%;">150% 百分比</span>

### 5.3 综合样式

<span style="font-family:'KaiTi'; font-size:20px; color:#b22222; font-weight:bold;">
楷体、20px、加粗、深红色
</span>

---

## 六、文本对齐方式（居中、居左、居右、两端对齐）

<!--
  Markdown 原生不支持对齐，需借助 HTML 的 <div> 或 <p> 标签配合 text-align 属性。
  可选值：left（左对齐，默认）、center（居中）、right（右对齐）、justify（两端对齐）。
  注意：块级元素需独占一行。
-->

### 6.1 左对齐（默认）

<div style="text-align:left;">
这是左对齐文本。这是左对齐文本。这是左对齐文本。这是左对齐文本。
</div>

### 6.2 居中

<div style="text-align:center;">
这是居中对齐文本。<br>
**可以包含加粗等格式**
</div>

### 6.3 右对齐

<div style="text-align:right;">
这是右对齐文本。
</div>

### 6.4 两端对齐

<div style="text-align:justify;">
这是两端对齐文本。两端对齐会让每行的左右两端都对齐，文字间距自动调整，适合排版较长的段落。这是两端对齐文本。两端对齐会让每行的左右两端都对齐，文字间距自动调整。
</div>

### 6.5 文字垂直居中（常用于图片+文字混排）

<div style="display:flex; align-items:center; justify-content:center; gap:12px;">
  <img src="https://cdn.jsdelivr.net/gh/AloneGoatProject/nomdn.github.io@main/img/goat.jpg" width="40" alt="icon">
  <span style="font-size:20px; font-weight:bold;">图标与文字垂直居中</span>
</div>

---

## 七、列表

<!--
  无序列表：使用 -、* 或 + 开头，注意符号后需有空格。
  有序列表：使用数字 + . 开头，数字可以不连续，渲染时会自动排序。
  任务列表：使用 - [ ] 或 - [x] 开头。
  嵌套列表：子项缩进 2~4 个空格。
-->

### 7.1 无序列表

- 苹果
- 香蕉
- 橙子
  - 赣南脐橙
  - 冰糖橙
- 葡萄

### 7.2 有序列表

1. 第一步：准备材料
2. 第二步：清洗食材
3. 第三步：开始烹饪
   1. 热锅
   2. 下油
   3. 翻炒
4. 第四步：装盘出锅

### 7.3 任务列表

- [x] 完成需求分析
- [x] 编写设计文档
- [ ] 实现核心功能
- [ ] 编写测试用例
- [ ] 部署上线

### 7.4 自定义列表项符号（HTML 方式）

<ul style="list-style-type:'★ '; color:#4a90e2;">
  <li>星星符号列表项一</li>
  <li>星星符号列表项二</li>
  <li>星星符号列表项三</li>
</ul>

---

## 八、引用（Blockquotes）

<!--
  引用：在每行开头使用 > 符号，可嵌套多层。
  引用内可以包含其他 Markdown 语法，如加粗、列表、代码等。
-->

> 这是一段引用文字。引用常用于摘录他人的言论或强调重要内容。

> 引用也可以嵌套：
> > 这是第二层引用
> > > 这是第三层引用

> 引用中可以使用其他格式：
> - **加粗** 和 *倾斜*
> - `行内代码`
> - [链接](https://example.com)

---

## 九、链接（Links）

<!--
  链接语法：[链接文字](链接地址 "可选标题")
  1. 外部链接：指向其他网站
  2. 内部链接：指向本站其他页面（相对路径）
  3. 锚点链接：指向当前页面或其他页面的某个标题
  4. 邮件链接：mailto:
  5. 参考式链接：将链接地址放在文末统一管理
-->

### 9.1 外部链接

访问 [小草文学部 GitHub 仓库](https://github.com/bbez-kjxxb/grass) 查看源码。

带提示文字的链接：[百度](https://www.baidu.com "点击前往百度")。

### 9.2 内部链接

- 前往 [主页](index.md)
- 前往 [联系我们](connect.md)

### 9.3 锚点链接（页面内跳转）

<!--
  锚点链接格式：[文字](#标题文字的小写拼音/英文，空格和特殊符号替换为连字符)
  中文标题的锚点在 Material 主题中通常取标题文字本身，建议用英文标题更稳妥。
-->

跳转到本文的 [表格](#十表格tables) 章节。

### 9.4 邮件链接

发送邮件：[联系站长](mailto:xtkdjxfitskg@163.com)

### 9.5 参考式链接

<!--
  先在正文中写 [链接文字][标识]，再在文末任意位置定义 [标识]: 地址
  适合链接较多时集中管理。
-->

这是 [Google][google] 和 [GitHub][github] 的参考式链接。

[google]: https://www.google.com "Google 搜索引擎"
[github]: https://github.com "全球最大代码托管平台"

### 9.6 自动链接

直接写 URL 会自动变为可点击链接：https://www.example.com

---

## 十、表格（Tables）

<!--
  表格语法：
  | 列1 | 列2 | 列3 |
  |-----|-----|-----|
  | a   | b   | c   |
  对齐方式：通过第二行的冒号控制
    :---  左对齐
    :---: 居中
    ---:  右对齐
-->

### 10.1 基础表格

| 姓名 | 年龄 | 职业 |
|------|------|------|
| 张三 | 25   | 工程师 |
| 李四 | 30   | 设计师 |
| 王五 | 28   | 产品经理 |

### 10.2 指定列对齐方式

<!--
  :--- 左对齐，:---: 居中，---: 右对齐
-->

| 左对齐 | 居中对齐 | 右对齐 |
|:-------|:--------:|-------:|
| 苹果   |  5.00 元 | 100 kg |
| 香蕉   |  3.50 元 | 200 kg |
| 橙子   |  4.20 元 | 150 kg |

### 10.3 表格中使用格式

| 功能 | 语法 | 效果 |
|------|------|------|
| 加粗 | `**文字**` | **文字** |
| 倾斜 | `*文字*` | *文字* |
| 行内代码 | `` `代码` `` | `代码` |
| 链接 | `[文字](url)` | [示例](https://example.com) |

---

## 十一、图片（Images）

<!--
  图片语法：![替代文字](图片地址 "可选标题")
  1. 网络图片：直接写 URL
  2. 本地图片：写相对路径（相对 md 文件所在目录）
  3. 调整大小：使用 HTML 的 <img> 标签，或借助 attr_list 扩展
  4. 图片链接：将图片放在链接语法中
-->

### 11.1 基础图片

![图标](../../icon/icon.png "favicon")

### 11.2 使用 HTML 控制图片尺寸和对齐

<!--
  通过 <img> 标签的 width、height 属性控制大小，
  配合 style="display:block; margin:auto;" 实现居中。
-->

<img src="../../icon/icon.png" alt="图标" width="80">

居中显示：

<div style="text-align:center;">
  <img src="../../icon/icon.png" alt="居中图标" width="100">
</div>

带边框和圆角的图片：

<img src="../../icon/icon.png" alt="圆角图标" width="100" style="border-radius:50%; border:3px solid #4a90e2;">

### 11.3 图片作为链接

<!--
  将 ![图片](地址) 放在 [ ](链接) 中，点击图片即可跳转。
-->

[![点击跳转 GitHub](../../icon/icon.png)](https://github.com/bbez-kjxxb/grass)

---

## 十二、视频（Videos）

<!--
  Markdown 原生不支持视频，需使用 HTML5 的 <video> 标签。
  常用属性：
    src       视频地址
    width/height  宽高
    controls  显示播放控件
    autoplay  自动播放（通常需配合 muted）
    loop      循环播放
    muted     静音
    poster    封面图地址
  支持格式：MP4、WebM、Ogg 等。
-->

### 12.1 基础视频

<video src="https://www.w3schools.com/html/mov_bbb.mp4" controls width="100%"></video>

### 12.2 带封面、循环、静音的视频

<video src="https://www.w3schools.com/html/movie.mp4" controls muted loop poster="https://cdn.jsdelivr.net/gh/AloneGoatProject/nomdn.github.io@main/img/goat.jpg" width="100%"></video>

### 12.3 多来源视频（兼容性更好）

<!--
  使用多个 <source> 标签，浏览器会选择第一个能播放的格式。
-->

<video controls width="100%">
  <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
  <source src="https://www.w3schools.com/html/mov_bbb.ogg" type="video/ogg">
  您的浏览器不支持视频播放。
</video>

### 12.4 嵌入 iframe 视频（如 B站、YouTube）

<!--
  通过 iframe 嵌入第三方视频平台的视频。
  注意：MkDocs 默认可能会过滤 iframe，如不显示需配置 site_url 或使用插件。
-->

<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=117291010301780&bvid=BV1RFe16zEvo&cid=41996848730&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" width="100%" height="400"></iframe>
---

## 十三、音频（Audio）

<!--
  使用 HTML5 的 <audio> 标签嵌入音频。
  常用属性与 video 类似：src、controls、autoplay、loop、muted。
  支持格式：MP3、WAV、OGG 等。
-->

### 13.1 基础音频

<audio src="https://www.w3schools.com/html/horse.mp3" controls></audio>

### 13.2 多来源音频

<audio controls>
  <source src="https://www.w3schools.com/html/horse.mp3" type="audio/mpeg">
  <source src="https://www.w3schools.com/html/horse.ogg" type="audio/ogg">
  您的浏览器不支持音频播放。
</audio>

### 13.3 带描述的音频

<div style="text-align:center;">
  <p style="color:#666;">🎵 示例音频（点击播放）</p>
  <audio src="https://www.w3schools.com/html/horse.mp3" controls></audio>
</div>

---

## 十四、提示框 / 警告框（Admonition）

<!--
  本项目已启用 admonition 扩展，Material 主题提供了丰富的提示框样式。
  语法：!!! 类型 "可选标题"
        内容（缩进 4 个空格）
  常用类型：note, abstract, info, tip, success, question, warning, failure, danger, bug, example, quote
  可折叠：把 !!! 改为 ??? 即可变成可折叠提示框。
-->

### 14.1 常用提示框

!!! note "笔记"
    这是一个笔记提示框，用于补充说明。

!!! info "信息"
    这是一个信息提示框，用于传达重要信息。

!!! tip "提示"
    这是一个提示框，用于给出实用建议。

!!! success "成功"
    操作已成功完成！

!!! warning "警告"
    请注意，这里可能存在风险。

!!! danger "危险"
    此操作不可逆，请谨慎执行！

!!! example "示例"
    这里是一个示例。

!!! quote "引用"
    这里是一段引用。

### 14.2 可折叠提示框

??? note "点击展开 / 收起"
    这是一个可折叠的提示框内容。

???+ tip "默认展开的提示框"
    使用 `???+` 可以让提示框默认展开。

---

## 十五、折叠块 / 详情（Details）

<!--
  本项目已启用 pymdownx.details 扩展，语法与 admonition 类似。
  使用 ??? 或 ???+ 开头，后面跟类型和标题。
  内容需缩进。
-->

??? question "什么是 Markdown？"
    Markdown 是一种轻量级标记语言，通过简单的文本格式来编写结构化文档。它由 John Gruber 于 2004 年创建，如今已成为技术文档的主流格式之一。

???+ example "展开查看代码示例"
    ```python
    print("Hello, Markdown!")
    ```

---

## 十六、水平分隔线

<!--
  使用三个以上的 -、* 或 _ 单独占一行，即可生成分隔线。
-->

---

***

___

---

## 十七、转义字符

<!--
  在特殊字符前加反斜杠 \，可使其显示为普通字符而非 Markdown 语法。
-->

以下是需要转义的常用字符：

| 字符 | 转义写法 | 显示效果 |
|------|----------|----------|
| `\\` | `\\` | \ |
| `\*` | `\*` | * |
| `\#` | `\#` | # |
| `\.` | `\.` | . |
| `\!` | `\!` | ! |
| `` \` `` | `` \` `` | ` |
| `\[` | `\[` | [ |
| `\(` | `\(` | ( |

示例：\*这不是倾斜\*，而是显示星号。

---

## 十八、综合示例：一篇排版精美的短文(以下内容全部虚构!!!)

<!--
  以下是一个综合运用各种语法的示例，展示如何排版一篇美观的文档。
-->

<div style="text-align:center;">

# 📖 小草文学部招新启事

<span style="font-family:'KaiTi'; font-size:18px; color:#555;">
—— 用文字记录青春，用墨香书写未来 ——
</span>

</div>

---

## 🎯 招新对象

<span style="color:#2c3e50;">
全体在校学生，**不限年级、不限专业**，只要你热爱文字，欢迎加入！
</span>

## ✨ 部门简介

> 小草文学部成立于 2018 年，是一个以**文学创作**、**读书分享**、**报纸编辑**为核心的学生社团。我们坚信：
> > *每一棵小草，都有属于自己的春天。*

## 📋 招新岗位

| 岗位 | 人数 | 要求 |
|:-----|:----:|:-----|
| 文字编辑 | 5 | 文笔流畅，有一定写作基础 |
| 美术编辑 | 3 | 熟练使用 PS 等设计软件 |
| 摄影记者 | 2 | 具备摄影器材及构图能力 |
| 新媒体运营 | 4 | 熟悉公众号、短视频运营 |

## 🎁 加入我们你将获得

- [x] 专业的写作指导与培训
- [x] 作品刊登在校报的机会
- [x] 结识志同道合的文学伙伴
- [ ] 一份难忘的青春回忆（等待你的书写）

## 📞 报名方式

!!! tip "扫码或联系我们"
    - 部长 QQ：`510866875`
    - 社团群 QQ：`912049006`
    - 邮箱：[510866875@qq.com](mailto:510866875@qq.com)

??? question "报名截止时间？"
    招新长期有效，欢迎随时加入！

<div style="text-align:center; color:#888; font-size:14px; margin-top:30px;">
—— 小草文学部，期待与你相遇 ——
</div>

---

<!--
  ========================================================================
  附录：常用速查表
  ========================================================================
-->

## 附录：常用语法速查表

| 功能 | 语法 | 说明 |
|------|------|------|
| 加粗 | `**文字**` | 粗体强调 |
| 倾斜 | `*文字*` | 斜体 |
| 删除线 | `~~文字~~` | 删除线 |
| 行内代码 | `` `代码` `` | 等宽字体显示 |
| 链接 | `[文字](地址)` | 超链接 |
| 图片 | `![替代](地址)` | 插入图片 |
| 代码块 | ```` ```语言 ```` | 带高亮代码块 |
| 引用 | `> 文字` | 引用块 |
| 分隔线 | `---` | 水平分隔线 |
| 无序列表 | `- 项目` | 圆点列表 |
| 有序列表 | `1. 项目` | 数字列表 |
| 任务列表 | `- [ ] 项目` | 复选框 |
| 表格 | `\| 列 \| 列 \|` | 表格 |
| 文字颜色 | `<span style="color:red">` | HTML 内联样式 |
| 居中 | `<div style="text-align:center">` | HTML 内联样式 |

---

<div style="text-align:center; color:#aaa; font-size:13px;">
本文档基于 MkDocs Material 主题编写，所有示例均可直接复制使用。
</div>