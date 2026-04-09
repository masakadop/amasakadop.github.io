# masakadop.github.io

Link to Bio サイトと、GitHub/Codex 連携ハウツー資料を管理するリポジトリです。

## スライド資料の場所

- ソース: `slides/how-to-codex.md`
- 公開URL(スライド): `https://masakadop.github.io/slides/how-to-codex/`

## デプロイ

`main` ブランチに push すると GitHub Actions (`.github/workflows/deploy-pages.yml`) が実行され、
`slides/how-to-codex.md` から Slidev で静的サイトをビルドし、`index.html` と一緒に GitHub Pages へデプロイします。
