# 印尼随身看

3 人、2026 年 9 月 29 日至 10 月 6 日的印尼旅行手册。

- 成品只有 `public/index.html`，不加载外部脚本、字体或样式。
- 页面按事件所在地时区计算倒计时，自动切换日间/夜间配色。
- 点击地点可打开 Google Maps；每日路线可展开并打开多点导航。
- 点击“保存离线手册”可下载当前完整 HTML，导航链接仍需联网。
- 火山与 Tumpak Sewu 住宿尚未确定，当前只显示为待办。

## Cloudflare Workers 自动发布

仓库包含 `wrangler.jsonc`，适合使用 Cloudflare Workers Static Assets。首次连接 GitHub 后，每次推送到生产分支都会自动部署。

Cloudflare 设置：

- 项目名称：`indonesia-pocket-guide`
- Production branch：`main`
- Root directory：`/`
- Build command：留空
- Deploy command：`npx wrangler deploy`

Cloudflare 建立项目后会提供公开的 `*.workers.dev` 地址。无需数据库、环境变量、域名或付费套餐。

## 更新行程

修改 `public/index.html` 后提交并推送到 `main`。Cloudflare 会自动重新发布。公开网页不应加入确认号、票号、证件号、私人手机号或邮箱。
