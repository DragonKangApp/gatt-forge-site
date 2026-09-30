# GATT Forge 支持与隐私静态网站

本目录是待补齐发布信息的网页，不是已经发布的网站。内容依据 `Docs/Release/Privacy-*.md`、`Support-FAQ-*.md`、`Privacy-Audit.md`、`metadata.json`，并核对当前权益、导出和数据工具源码。中英文隐私正文保留原草稿全部章节与数据边界。

## 文件与预览

- `index.html`：英文 Support / FAQ；`privacy.html`：英文隐私政策。
- `zh/index.html`：中文支持；`zh/privacy.html`：中文隐私政策。
- `styles.css`：共用深蓝/青色响应式样式；`favicon.svg`：本地矢量图标；`.nojekyll`：静态发布标记。

直接用浏览器打开 `index.html` 即可；中英文切换、隐私链接与 CSS 均为相对路径，支持 `file://`、站点根目录和仓库子路径。无需构建、依赖、JavaScript、CDN 或网络字体。页面没有 Cookie、分析脚本、表单和自动网络请求。

如需 HTTP 本地预览，在本目录运行（需要本机 Python 3）：

```sh
python3 -m http.server 8765 --bind 127.0.0.1
```

访问 `http://127.0.0.1:8765/`，完成后 Ctrl-C 停止。分别检查四个页面、320–390px 窄屏和桌面宽度、中文字体、键盘焦点与语言切换。

## 发布前 TODO（中英文都要同步）

- 支持邮箱已设为 `dragon_kang_app@163.com`，四个页面均提供邮件链接；请用户确认邮箱可正常收信。
- `TODO_DEVELOPER_NAME`：实际开发者 / 运营者公开名称。
- `TODO_EFFECTIVE_DATE`：政策实际生效日期，不用文件制作日期冒充。
- 站点根地址已确定：`https://dragonkangapp.github.io/gatt-forge-site/`；是否已上线需以实际部署结果为准。
- `TODO_SUPPORT_MESSAGE_HANDLING`：实际收件人、邮件服务商、处理用途、保留期限、删除请求途径。不要未经确认承诺“立即删除”或“不接收任何数据”。
- `TODO_HOSTING_PRIVACY`：选定托管服务后，确认其访问日志、IP 等服务端处理，并补充对应政策链接；页面自身无跟踪不代表托管方不记日志。

核对最终二进制与运营实际后，移除四页的“发布准备稿 / Publication draft”提示以及待填说明。审计所提应用内隐私入口仍是之后单独的发布任务；本轮未改应用代码，也未填写 App Privacy 表单。

## 手动发布到 GitHub Pages

推荐使用独立的公开网页仓库，只放本目录的网页资产，避免把 iOS 源码、测试日志或公司资料一并公开。仓库已由用户创建：https://github.com/DragonKangApp/gatt-forge-site 。本目录作为独立 Git 仓库提交与推送；以下步骤用于手动核对 Pages 配置。

1. 用户自己创建 / 选择一个用于网站的仓库；将本目录的四个 HTML、`zh/`、`styles.css`、`favicon.svg`、`.nojekyll` 放到该仓库根目录，保留目录结构。
2. 在仓库 Settings → Pages，选择 **Deploy from a branch**，选择实际发布分支和 **/(root)**，保存。
3. 发布完成后，使用 GitHub 显示的实际 HTTPS 地址，不自行猜测用户名、仓库名或域名。
4. 确认英文首页、`privacy.html`、`zh/index.html`、`zh/privacy.html` 均无需登录即可访问，且小屏、CSS、语言互跳正常。替换 TODO 后再次检查再用于提交。

GitHub 的分支发布源只提供仓库根目录或 `/docs`，不能在下拉框直接选当前工程的 `Docs/Site/`。若坚持从整个工程仓库发布，需自行设置上传此目录的 GitHub Actions 工作流，或明确调整网站发布目录；不要误把整个工程作为公开站点。本轮不生成或启用自动部署。

其他静态托管：将本目录内容作为发布根目录上传，保留相对路径，无需后端。启用 HTTPS；核对托管方访问日志与隐私说明。

依据：[GitHub Pages 发布源说明](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)，核对日期 2026-09-30。

## App Store Connect 最终填写的两个 URL

以下为已确定的目标地址；应确认 Pages 实际可访问并补全其余 TODO 后再用于提交：

- English Support URL：`https://dragonkangapp.github.io/gatt-forge-site/`
- English Privacy Policy URL：`https://dragonkangapp.github.io/gatt-forge-site/privacy.html`
- 简体中文 Support URL：`https://dragonkangapp.github.io/gatt-forge-site/zh/`
- 简体中文 Privacy Policy URL：`https://dragonkangapp.github.io/gatt-forge-site/zh/privacy.html`

分别用于对应本地化的 Support URL / Privacy Policy URL 字段。取得公开 URL 后再填写，并按最终 App Store Connect 界面核对。不要把 GitHub 仓库文件浏览地址或本地 `file://` 地址填入。
