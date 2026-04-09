# masakadop.github.io

Link to Bio サイトと、GitHub/Codex 連携ハウツー資料を管理するリポジトリです。

## スライド資料の場所

- スライドエントリ: `slides/how-to-codex.html`
- スライド本文(Markdown): `slides/how-to-codex.md`
- 公開URL(スライド): `https://masakadop.github.io/slides/how-to-codex/`

## デプロイ

`main` ブランチに push すると GitHub Actions (`.github/workflows/deploy-pages.yml`) が実行され、
`index.html` と `slides/` ディレクトリをそのまま GitHub Pages へデプロイします。

`slides/how-to-codex.html` は remark.js を使って `slides/how-to-codex.md` を実行時にレンダリングするため、
Slidev のような事前ビルド工程は不要です。
