# blog

共同ブログ

## Decap CMS

GitHub Pages 上で Decap CMS を使えるように、管理画面を [`/admin/`](/Users/tomoki-ono/workspace/itoya-blog/static/admin/index.html) に追加しています。

### URL

- 本番サイト: `https://itoya-engei.github.io/blog/`
- 管理画面: `https://itoya-engei.github.io/blog/admin/`

### 現在の編集対象

- `content/posts` 配下の投稿
- `content/about.md`

### 初回セットアップ

Decap の `github` backend は、そのままでは GitHub Pages 上でログインできません。認証用の OAuth プロバイダを別途 1 つ用意してください。

選択肢:

- Netlify を使う: `https://api.netlify.com/auth/done` を callback URL にした GitHub OAuth App を作成し、Netlify 側で Decap 認証を有効化する
- 自前で用意する: Decap の `auth` エンドポイントを Cloudflare Workers / Netlify Functions / Vercel などで立てる

用意できたら [`static/admin/config.yml`](/Users/tomoki-ono/workspace/itoya-blog/static/admin/config.yml) の `backend` 設定に必要な値を入れてください。

必要になりやすい項目:

- `base_url`
- `auth_endpoint`
- 必要に応じて `site_domain`

OAuth プロバイダ未設定の間も、管理画面自体は公開されますがログインは完了しません。
