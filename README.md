# masakadop.github.io

Link to Bio サイトと、GitHub/Codex 連携ハウツー資料を管理するリポジトリです。

## スライド資料の場所

- スライド本文(Markdown): `slides/how-to-codex.md`
- 公開URL(スライド): `https://slides.deno.dev/html?url=https://masakadop.github.io/slides/how-to-codex.md`

## デプロイ

`main` ブランチに push すると GitHub Actions (`.github/workflows/deploy-pages.yml`) が実行され、
`index.html` と `slides/` ディレクトリをそのまま GitHub Pages へデプロイします。

スライド表示は `slides.deno.dev` を利用し、`slides/how-to-codex.md` を直接参照します。
