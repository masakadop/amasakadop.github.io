# masakadop.github.io

Link to Bio サイトと、Slidevで作成した GitHub/Codex 連携ハウツースライドを管理するリポジトリです。

## スライドの場所

- ソース: `slides/how-to-codex.md`
- 公開URL: `https://masakadop.github.io/how-to-codex/`

## ローカルビルド

```bash
npm install
npm run build:slides
```

## デプロイ

`main` ブランチに push すると GitHub Actions (`.github/workflows/deploy-pages.yml`) が実行され、
`index.html` と `how-to-codex` スライドを GitHub Pages へデプロイします。
