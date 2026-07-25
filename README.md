# Han Yan 学术网站维护说明

这是一个仅面向 PC 桌面端的单页网站，不需要安装框架、数据库或后台系统。

日常维护主要只需要修改两个文件：

- `index.html`：修改姓名、简介、论文、课程、链接和日期等文字内容。
- `site-settings.css`：修改字体大小、颜色、页面宽度、左栏宽度和间距。

`style.css` 保存网站的结构样式，通常不需要修改。

## 本地预览

可以直接双击 `index.html` 在浏览器中打开。

也可以在网站文件夹中运行：

```bash
python -m http.server 8000
```

然后访问 `http://localhost:8000`。

## 修改字体、颜色和布局

打开 `site-settings.css`。所有常用设置都集中在文件顶部，并有注释说明。

例如：

```css
--body-font-size: 16px;          /* 正文字号 */
--profile-name-alignment: center;/* 姓名对齐：left 或 center */
--profile-title-size: 0.94rem;   /* 照片下方的职位字号 */
--section-heading-size: 2.375rem;/* Research、Teaching 标题字号 */
--page-width: 1120px;            /* 页面总宽度 */
--profile-column-width: 250px;   /* 左侧个人信息栏宽度 */
--column-gap: 4.5rem;            /* 左右两栏之间的距离 */
--accent: #163f65;               /* 链接和强调色 */
```

修改数值、保存文件并刷新浏览器即可看到效果。

## 修改文字内容

打开 `index.html`，搜索 `UPDATE:`。这些 HTML 注释标出了以下位置：

- Biography
- Research papers
- Publication status
- Teaching
- Profile links
- Last-updated date

只修改注释附近的文字即可，不要删除 HTML 标签的尖括号。

## 添加或修改论文

在 `index.html` 中搜索 `PAPER TEMPLATE`，复制完整的 `<article class="paper">...</article>` 模板，并放入 Publications 或 Working Papers 对应的 `.paper-list` 中。

填写论文标题、合作者、状态、摘要和链接。没有的 Paper、Data、Code 或 Slides 链接可以直接删除。

每篇论文的摘要使用原生 `<details>`，不需要 JavaScript。

## 更换照片、CV 或其他文件

- 照片：用新文件覆盖 `assets/profile.jpg`。
- CV：用新文件覆盖 `assets/Han_Yan_CV.pdf`。
- 论文或课件：放入 `assets` 文件夹，并在 `index.html` 中填写对应路径。

保持原文件名时，不需要修改网站代码。如果使用新文件名，需要同步修改 `index.html` 中的链接。

## 发布到 GitHub Pages

1. 把 `index.html`、`site-settings.css`、`style.css`、`README.md` 和 `assets` 文件夹上传到 GitHub 仓库。
2. 在仓库中打开 **Settings → Pages**。
3. 在 **Build and deployment** 中选择 **Deploy from a branch**。
4. 选择 `main` 分支和 `/ (root)` 文件夹，然后保存。
5. GitHub 完成部署后会显示网站地址。
