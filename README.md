# 赌石四人局 · Vercel 部署包

你控制A，与三位电脑完成六轮竞拍、开窗、接盘、鉴料和切石。完整游戏代码集中在 `public/index.html`，包含 HTML、CSS、JavaScript 和 SVG，无第三方依赖，无需安装或构建。

## 项目结构

```text
jade-auction-vercel/
├── public/
│   └── index.html     # 完整可玩的游戏，也是网站首页
├── vercel.json       # Vercel 静态部署配置
├── README.md
└── .gitignore
```

## 通过 GitHub 部署到 Vercel

1. 解压部署包，进入 `jade-auction-vercel` 文件夹。
2. 在 GitHub 新建仓库，将这个文件夹**里面的内容**上传到仓库根目录。可用网页的 **Add file → Upload files**，拖入 `public` 文件夹、`vercel.json`、`README.md`；`.gitignore` 也可一并上传。提交后确认仓库根目录能直接看到 `vercel.json`，且存在 `public/index.html`。
3. 在 Vercel 新建项目，导入这个 GitHub 仓库。
4. 检查设置后部署：

| 设置 | 值 |
| --- | --- |
| Framework Preset | `Other` |
| Root Directory | `./`，即仓库根目录 |
| Build Command | 留空，跳过构建 |
| Output Directory | `public` |
| Install Command | 无需设置 |
| Environment Variables | 无需设置 |

`vercel.json` 已声明框架、构建命令和输出目录。部署完成后访问 Vercel 返回的地址即可试玩。

请上传解压后的项目内容，**不是 ZIP 文件本身**。如果 GitHub 根目录下多包了一层 `jade-auction-vercel/`，需把 Vercel 的 Root Directory 改为这一层；按第2步上传则保持 `./`。

## 本地试玩和后续修改

- 直接用浏览器打开 `public/index.html`，点击“开始六轮对局”。
- 后续修改同一个 HTML 文件并提交、推送到 GitHub；默认配置下，Vercel 会自动触发对应部署。
- 本包中的 HTML 与已完成的试玩文件逐字节一致，未改动游戏逻辑。
- 部署后仍是每位访问者各自在浏览器内进行的人机对局，不共享牌局或进度；刷新页面会重置当前对局。

官方说明：[Vercel 静态项目构建设置](https://vercel.com/docs/builds/configure-a-build)、[Vercel 配置文件](https://vercel.com/docs/project-configuration/vercel-json)、[GitHub 集成与自动部署](https://vercel.com/docs/git/vercel-for-github)、[GitHub 网页上传文件](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)。
