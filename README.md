# homepage-demo

个人主页。**全部内容在一个 `index.html` 里** —— 零依赖、无构建步骤、无 CDN 和外部字体。

双击 `index.html` 就能离线打开，也可以直接丢到 GitHub Pages。

## ⚠️ 发布前必须替换

页面里的**公司名、时间、项目数据、工作成果全部是搭建时自拟的示例，不是真实经历**。
`index.html` 顶部有一段 HTML 注释列出了具体哪些是虚构的。

用真名发布不实履历是有风险的，请先改成你自己的再上线。

真实信息只有两处：姓名「杨开智」、GitHub 地址 `github.com/yykkzz0123`。

## 改成你自己的

用记事本或 VS Code 打开 `index.html`，搜索定位即可：

| 想改什么 | 搜索 |
| --- | --- |
| 浏览器标签标题、SEO 描述 | `<title>`、`<meta name="description">` |
| 首屏名字和一句话介绍 | `class="hero"` 区块 |
| 头像上的字 | `class="avatar"`（目前是「杨」，可换成名字缩写） |
| 关于、技能清单 | `id="about"`、`id="skills"` |
| 项目卡片 | `id="projects"`，每个 `<article class="card">` 是一张 |
| 工作经历 | `id="experience"`，每个 `<li>` 是一条 |
| 邮箱、GitHub | `id="contact"` |
| 配色 | 文件开头 `:root`（浅色）和 `[data-theme="dark"]`（深色） |
| 字号、间距、圆角 | 文件开头的设计令牌 |

换配色只需要改 `--accent` 和 `--accent-ink` 两个变量，其余颜色都由它们派生。

## 已实现

- **深色 / 浅色主题** —— 跟随系统偏好，手动切换后记入 `localStorage`，刷新保持
- **滚动入场动画** —— 基于 `IntersectionObserver`，尊重系统「减少动态效果」设置
- **导航高亮** —— 滚动时自动标记当前章节
- **响应式** —— 窄屏下导航折叠为下拉菜单，点链接自动收起
- **无障碍** —— 语义化标签、跳转链接、可见焦点环、`aria-expanded` 状态同步

## 部署

纯静态单文件，任何静态托管都能直接用：

- **GitHub Pages** —— 仓库 Settings → Pages → Source 选 `main` 分支根目录
- **Vercel / Netlify** —— 拖拽这个文件夹，无需配置构建命令
