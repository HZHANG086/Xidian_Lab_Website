## 智能机器人和工业检测实验室网站维护说明

本网站为静态页面，主要文件：

- 首页：`index.html`
- 子页面：`projects.html`（项目）、`achievements.html`（科研成果）、`activities.html`（我们的活动）、`join.html`（加入我们）
- 样式：`style.css`

### 1. 一般维护原则

- **只改内容，不动结构**：
  - 修改文案时，只在标注为“常改内容”的 section 内修改文字。
  - 不要删除或随意修改 `<div class="card">`、`<ul class="achievement-list">`、`.member-card` 等结构和类名。
- **不写内联样式**：不要在标签上增加 `style="..."`，统一在 `style.css` 中改样式。

### 2. 各页面内容如何更新

#### 首页 `index.html`

- 实验室简介与 PI 履历：在 “关于实验室” section 内修改段落文字和时间轴内容。
- 研究方向：在 “研究领域” section 的两行 `<div class="field-box">` 中修改标题文字。
- 代表项目：在 “代表项目” section 中，每个项目对应一个 `.card`，复制一整块修改标题、时间和简介即可。
- 代表科研成果：在 `<ul class="achievement-list">` 里增删 `<li>`，并保持每条一行。
- 团队成员：在 `.member-grid` 里的每个 `.member-card` 中修改姓名、头衔和简介；如需新增成员，复制一整块 `.member-card`。
- 合作单位：在 “外部合作方” section 中为每个合作单位增加一个 `.partner-item`。
- 加入我们引导：只需修改说明文字或链接指向。

#### 项目、成果、活动、加入我们

- `projects.html`：每个项目是一个 `.card` 区块，复制一整块修改内容即可。
- `achievements.html`：按“论文 / 专利 / 奖励”三段结构增删 `.card`。
- `activities.html`：每个活动是一块 `.card activity-card`，复制修改标题、时间和描述。
- `join.html`：在 `.card--highlight` 中修改岗位和要求，在 `.card--contact` 中修改联系方式。

### 3. 图片更换约定

建议在网站根目录下按以下结构存放图片（可自行创建目录）：

- 首页头图：`images/hero.jpg`
- 成员头像：`images/members/xxx.jpg`
- 活动图片：`images/events/xxx.jpg`

示例（成员头像）：

- 在 `index.html` 中，将某个成员头像块从
  ```html
  <div class="avatar" aria-hidden="true"></div>
  ```
  替换为
  ```html
  <div class="avatar">
      <img src="images/members/zhangsan.jpg" alt="张三">
  </div>
  ```
  并确保证图片文件存在于对应路径。

活动图片可采用类似方式，将 `.activity-img` 换成 `<img src="images/events/xxx.jpg" class="activity-img" alt="活动名称">`，`style.css` 已对该类设置统一尺寸。

### 4. 布局和排版建议

- 尽量控制单条文案长度，成员介绍建议 2–3 行内。
- 不建议在内容文本中加入 `<br>` 或额外的内联样式，避免在不同设备上排版错乱。

如需大幅度调整布局或样式，建议先备份当前文件，再在本地浏览器预览确认无误后提交到 GitHub。

