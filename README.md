# 曜宇 · Studio · One Page Portfolio

一个一页式作品集 / 产品落地页模板，基于 [Start Bootstrap - Creative](https://startbootstrap.com/theme/creative/)（Bootstrap 5.2.3）定制：主色改为深青 `#1f7a8c`，品牌名改为「曜宇 · Studio」，并在首页新增「快速开始」三步引导卡片。

本文档为中英双语：**前半部分为中文，后半部分为 English**，两部分内容一致，可任选其一阅读。

- 仓库：[github.com/xup1zqz/startbootstrap-creative](https://github.com/xup1zqz/startbootstrap-creative)
- 上游：[github.com/StartBootstrap/startbootstrap-creative](https://github.com/StartBootstrap/startbootstrap-creative)
- 许可：MIT（沿用上游 [LICENSE](./LICENSE)，Copyright 2013-2023 Start Bootstrap LLC）

---

# 中文

## 一、项目介绍

整站只有一页，从上到下依次是：全屏头图（Masthead）、品牌介绍（About）、**快速开始引导卡片（Quick Start）**、服务条目（Services）、作品网格（Portfolio）、下载引导（Call to Action）、联系方式（Contact）。

源码使用 Pug 写结构、SCSS 写样式，通过 npm 脚本编译进 `dist/` 目录；`dist/` 里是纯静态文件，可以直接丢到任何静态托管上。

技术栈：Bootstrap 5.2.3 · Pug 3 · Sass · Bootstrap Icons 1.5 · SimpleLightbox 2.1 · Browser Sync。

## 二、功能列表

- **一页式响应式布局**：桌面三栏 / 四栏，移动端自动堆叠，导航在小屏折叠为汉堡菜单。
- **吸顶导航**：页面滚动后导航栏自动收缩（`navbar-shrink`），点击锚点后移动端菜单自动收起。
- **全屏头图 Masthead**：背景图 + 渐变遮罩，支持自定义标题与标语。
- **品牌介绍 About**：主题色背景区块，带分隔线与跳转按钮。
- **快速开始引导卡片 Quick Start**：三步引导（选择 AI 模型 → 输入问题 → 获取回答），每步含圆形序号徽章与图标；`md` 断点以上用虚线连接三步，移动端自动隐藏连接线并纵向堆叠；底部带 CTA 按钮。
- **服务条目 Services**：四宫格图标卡片，可增删。
- **作品网格 Portfolio**：六宫格图片墙，点击用 SimpleLightbox 打开灯箱大图。
- **联系表单 Contact**：浮动标签表单，已预集成 [SB Forms](https://startbootstrap.com/solution/contact-forms)，填入 API Token 即可收消息。
- **主题可定制**：主色与辅助色集中在 `src/scss/variables/_colors.scss`，改两个变量即可全站换色。
- **源码可编译**：Pug + SCSS 源码分离，`npm start` 边改边预览，`npm run build` 一键产出 `dist/`。

## 三、安装步骤

前置条件：已安装 [Node.js](https://nodejs.org) 16 或更高版本（自带 npm）。

```bash
# 1. 克隆仓库
git clone https://github.com/xup1zqz/startbootstrap-creative.git

# 2. 进入目录
cd startbootstrap-creative

# 3. 安装依赖
npm install

# 4. 启动本地预览（自动打开浏览器并监听文件变化）
npm start
```

`npm start` 会先构建一次，再用 Browser Sync 起服务，默认访问 <http://localhost:3000>。修改 `src/` 下任意文件后浏览器会自动刷新。

## 四、使用说明

### 4.1 目录结构

```
startbootstrap-creative/
├── src/                        # 源码（改这里）
│   ├── pug/index.pug           # 整页结构，所有文案都在这里
│   ├── scss/
│   │   ├── styles.scss         # 样式入口，import 各分区
│   │   ├── variables/          # _colors.scss（主题色）_typography.scss _spacing.scss
│   │   ├── components/         # _navbar.scss _buttons.scss _dividers.scss
│   │   └── sections/           # _masthead.scss _quickstart.scss _portfolio.scss
│   ├── js/scripts.js           # 导航收缩、菜单收起、灯箱初始化
│   └── assets/                 # 图片与 favicon
├── dist/                       # 构建产物（纯静态，可直接部署）
├── scripts/                    # 构建脚本
└── package.json
```

### 4.2 常用命令

| 命令 | 说明 |
| --- | --- |
| `npm install` | 安装依赖 |
| `npm start` | 构建并启动本地预览（监听 `src/` 变化自动刷新） |
| `npm run build` | 全量构建，产物写入 `dist/` |
| `npm run build:pug` | 只编译 Pug → `dist/index.html` |
| `npm run build:scss` | 只编译 SCSS → `dist/css/styles.css` |
| `npm run build:scripts` | 只拷贝 JS → `dist/js/scripts.js` |
| `npm run build:assets` | 只拷贝图片等静态资源 |
| `npm run clean` | 删除 `dist/`，为重新构建做准备 |
| `npm run start:debug` | 以调试模式运行 |

### 4.3 修改主题色

编辑 `src/scss/variables/_colors.scss`：

```scss
$brand: #1f7a8c;   // 主色（当前：深青）
$overlay: #0b3d47; // 辅助色 / 遮罩色（当前：墨青）
$primary: $brand;  // 映射到 Bootstrap 的 primary
```

改完重新构建即可全站生效，不需要逐个文件替换颜色。

### 4.4 修改文案与标语

全部在 `src/pug/index.pug` 里：

- `title` —— 浏览器标签页标题
- `.navbar-brand` —— 左上角品牌名
- `header.masthead` 内的 `h1` —— 头图主标语
- `header.masthead` 内的 `p.text-white-75` —— 头图副标语
- 页脚 `footer` —— 版权信息

### 4.5 修改快速开始卡片

位于 `src/pug/index.pug` 的 `section#quickstart`（在 About 与 Services 之间）。三步各占一个 `.col-md-4`，结构为：序号徽章 `.quickstart-step-number` + Bootstrap Icon + 标题 + 说明文字。

- 增删步骤：复制或删除一个 `.col-md-4` 块，同时把栅格类改成对应列数（如四步改 `.col-md-3`）；
- 换图标：把 `i.bi-cpu` / `i.bi-pencil-square` / `i.bi-lightning-charge` 换成 [Bootstrap Icons](https://icons.getbootstrap.com/) 中任意图标类名；
- 改样式：编辑 `src/scss/sections/_quickstart.scss`（卡片圆角阴影、序号徽章、虚线连接线都在那里）；
- 导航栏的 `Quick Start` 入口在 `index.pug` 的 `ul.navbar-nav` 中，随锚点 `#quickstart` 自动跳转。

### 4.6 启用联系表单

表单默认预集成了 SB Forms：到 <https://startbootstrap.com/solution/contact-forms> 注册，绑定域名后拿到 access key，把它替换掉 `index.pug` 里 `data-sb-form-api-token='API_TOKEN'` 的 `API_TOKEN` 即可。

不使用 SB Forms 的话，删掉表单上的 `data-sb-*` 属性，并移除 `</body>` 前那行 `sb-forms-latest.js` 的 script 引用。

### 4.7 构建与发布

```bash
npm run build   # 产出最新 dist/
```

`dist/` 是纯静态文件，可以直接上传到任意静态托管。用 GitHub Pages 时，在仓库 Settings → Pages 里选择 `gh-pages` 分支或 `master` 分支的 `/dist` 目录作为发布来源即可。

> 提示：`dist/` 在本仓库是被 Git 跟踪的（`.gitignore` 只忽略 `node_modules` 和 `.DS_Store`），所以构建产物的变化会一并提交。

### 4.8 常见问题

**`npm run build` 报错 / 卡在清理步骤？** 该命令会先执行 `npm run clean` 删除整个 `dist/`。在某些受限制的运行环境（如沙箱、CI 容器）里这一步可能被权限策略拦下，可改用分步构建，效果相同：

```bash
npm run build:pug && npm run build:scss && npm run build:scripts && npm run build:assets
```

**改了 `src/` 但页面没变化？** 浏览器显示的是 `dist/` 的产物，改完源码必须重新构建（或保持 `npm start` 运行，它会自动重建）。

---

# English

## 1. Project Introduction

A one page portfolio / product landing template based on [Start Bootstrap - Creative](https://startbootstrap.com/theme/creative/) (Bootstrap 5.2.3). This fork swaps the default orange for a deep teal (`#1f7a8c`), renames the brand to **曜宇 · Studio**, and adds a three-step **Quick Start** guide card to the home page.

The page flows top to bottom: full-screen Masthead → About → **Quick Start** → Services → Portfolio → Call to Action → Contact.

Markup is written in Pug and styles in SCSS, compiled into `dist/` by npm scripts. Everything in `dist/` is plain static HTML/CSS/JS and can be hosted anywhere.

Stack: Bootstrap 5.2.3 · Pug 3 · Sass · Bootstrap Icons 1.5 · SimpleLightbox 2.1 · Browser Sync.

## 2. Features

- **One page responsive layout** — multi-column on desktop, stacked on mobile; nav collapses into a hamburger menu on small screens.
- **Sticky navbar** — shrinks on scroll (`navbar-shrink`) and auto-closes the mobile menu after an anchor click.
- **Full-screen masthead** — background image with gradient overlay, with editable title and tagline.
- **About section** — brand-colored band with divider and CTA button.
- **Quick Start guide card** — three steps (Pick an AI model → Ask your question → Get the answer), each with a numbered badge and icon. Steps are joined by a dashed connector above the `md` breakpoint; on mobile the connector is hidden and the steps stack vertically. A CTA button sits at the bottom of the card.
- **Services** — four icon cards, easy to add or remove.
- **Portfolio grid** — six image tiles that open in a SimpleLightbox lightbox.
- **Contact form** — floating-label form pre-integrated with [SB Forms](https://startbootstrap.com/solution/contact-forms); drop in your API token and it works.
- **Themeable** — brand and overlay colors live in one file, `src/scss/variables/_colors.scss`.
- **Compiled source** — Pug + SCSS sources with live reload via `npm start` and one-command builds via `npm run build`.

## 3. Installation

Requires [Node.js](https://nodejs.org) 16+ (npm is bundled).

```bash
# 1. Clone the repo
git clone https://github.com/xup1zqz/startbootstrap-creative.git

# 2. Move into it
cd startbootstrap-creative

# 3. Install dependencies
npm install

# 4. Start the local preview (opens your browser and watches for changes)
npm start
```

`npm start` builds once, then serves the site with Browser Sync at <http://localhost:3000>. Any change under `src/` triggers a rebuild and a browser refresh.

## 4. Usage

### 4.1 Project Structure

```
startbootstrap-creative/
├── src/                        # Source files (edit these)
│   ├── pug/index.pug           # Whole page markup; all copy lives here
│   ├── scss/
│   │   ├── styles.scss         # Style entry point, imports every partial
│   │   ├── variables/          # _colors.scss (theme colors) _typography.scss _spacing.scss
│   │   ├── components/         # _navbar.scss _buttons.scss _dividers.scss
│   │   └── sections/           # _masthead.scss _quickstart.scss _portfolio.scss
│   ├── js/scripts.js           # Navbar shrink, menu collapse, lightbox init
│   └── assets/                 # Images and favicon
├── dist/                       # Build output (static, deploy as is)
├── scripts/                    # Build scripts
└── package.json
```

### 4.2 npm Scripts

| Command | Description |
| --- | --- |
| `npm install` | Install dependencies |
| `npm start` | Build and serve locally with live reload |
| `npm run build` | Full build into `dist/` |
| `npm run build:pug` | Compile Pug → `dist/index.html` |
| `npm run build:scss` | Compile SCSS → `dist/css/styles.css` |
| `npm run build:scripts` | Copy JS → `dist/js/scripts.js` |
| `npm run build:assets` | Copy static assets |
| `npm run clean` | Delete `dist/` before a fresh build |
| `npm run start:debug` | Run in debug mode |

### 4.3 Change the Theme Colors

Edit `src/scss/variables/_colors.scss`:

```scss
$brand: #1f7a8c;   // Primary color (current: deep teal)
$overlay: #0b3d47; // Overlay / secondary color
$primary: $brand;  // Mapped onto Bootstrap's $primary
```

Rebuild and the new color applies site-wide — no per-file color replacement needed.

### 4.4 Change Copy and Taglines

Everything lives in `src/pug/index.pug`:

- `title` — browser tab title
- `.navbar-brand` — brand name in the navbar
- `h1` inside `header.masthead` — hero headline
- `p.text-white-75` inside `header.masthead` — hero sub-headline
- `footer` — copyright line

### 4.5 Edit the Quick Start Card

It lives in `section#quickstart` in `src/pug/index.pug` (between About and Services). Each step is a `.col-md-4` block containing a `.quickstart-step-number` badge, a Bootstrap Icon, a heading, and a short description.

- Add or remove steps: duplicate or delete a `.col-md-4` block and adjust the grid class (e.g. `.col-md-3` for four steps).
- Swap icons: replace `i.bi-cpu` / `i.bi-pencil-square` / `i.bi-lightning-charge` with any class from [Bootstrap Icons](https://icons.getbootstrap.com/).
- Restyle: edit `src/scss/sections/_quickstart.scss` (card radius/shadow, number badges, dashed connector).
- The navbar's **Quick Start** link is in `ul.navbar-nav` and points at `#quickstart`.

### 4.6 Enable the Contact Form

The form ships pre-wired for SB Forms. Sign up at <https://startbootstrap.com/solution/contact-forms>, register your domain, copy the access key, and replace `API_TOKEN` in `data-sb-form-api-token='API_TOKEN'` inside `index.pug`.

If you don't use SB Forms, remove the `data-sb-*` attributes from the form and delete the `sb-forms-latest.js` script tag before `</body>`.

### 4.7 Build and Deploy

```bash
npm run build   # refresh dist/
```

`dist/` is plain static output — upload it to any static host. For GitHub Pages, go to Settings → Pages and publish from the `gh-pages` branch or from the `/dist` folder on `master`.

> Note: `dist/` is tracked in Git here (`.gitignore` only excludes `node_modules` and `.DS_Store`), so build output changes are committed along with the source.

### 4.8 Troubleshooting

**`npm run build` fails or hangs on the clean step?** The command starts with `npm run clean`, which deletes the whole `dist/` directory. In restricted environments (sandboxes, some CI containers) that deletion can be blocked by policy. Run the build step by step instead — same result:

```bash
npm run build:pug && npm run build:scss && npm run build:scripts && npm run build:assets
```

**Edited `src/` but the page didn't change?** The browser renders `dist/`. Rebuild after editing sources, or keep `npm start` running so it rebuilds automatically.

---

## 版权与许可 / Copyright and License

本项目是 [Start Bootstrap - Creative](https://startbootstrap.com/theme/creative/) 的定制分支，模板版权归原作者所有。

Copyright 2013-2023 Start Bootstrap LLC. Code released under the [MIT](./LICENSE) license. Start Bootstrap was created and is maintained by [David Miller](https://davidmiller.io/).

This project is a customized fork of [Start Bootstrap - Creative](https://startbootstrap.com/theme/creative/); the template copyright belongs to its original author.
