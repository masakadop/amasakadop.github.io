# masakadop.github.io

Link to Bio サイトと、GitHub/Codex 連携ハウツー資料を管理するリポジトリです。

## スライド資料の場所

- ソース: `slides/how-to-codex.md`
- 公開URL(スライド): `https://masakadop.github.io/slides/how-to-codex.html`
- Markdownソース: `https://masakadop.github.io/slides/how-to-codex.md`

## デプロイ

`main` ブランチに push すると GitHub Actions (`.github/workflows/deploy-pages.yml`) が実行され、
`index.html` / `slides/how-to-codex.md` / `slides/how-to-codex.html` をそのまま GitHub Pages へデプロイします。

> 現在はビルドを行わない構成です。Node.js / npm のセットアップは不要です。
