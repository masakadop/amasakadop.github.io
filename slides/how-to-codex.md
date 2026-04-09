---
theme: seriph
background: https://images.unsplash.com/photo-1518770660439-4636190af475?auto=format&fit=crop&w=1600&q=80
title: GitHubアカウント作成→Codex連携→Link to Bioへ公開
info: |
  GitHub初心者向けの実践手順
class: text-center
transition: slide-left
mdc: true
---

# GitHubアカウント作成 → Codex連携
## → Link to BioでGitHub Pages公開

手順をこのスライド1本で。

<div class="pt-8">
  <span class="px-2 py-1 rounded bg-white/20">対象: はじめての人向け</span>
</div>

---
layout: section
---

# 0. 全体像

---

# 今日やること（3ステップ）

1. **GitHubアカウントを作る**
2. **Codex(CLI)をGitHubと連携する**
3. **GitHub Pagesで公開してLink to Bioに追加**

> ゴール: `https://masakadop.github.io/how-to-codex/` を公開し、プロフィールに導線を置く

---
layout: section
---

# 1. GitHubアカウント作成

---

# GitHubアカウント作成

1. `https://github.com/signup` を開く
2. メールアドレス・パスワード・ユーザー名を設定
3. メール認証を完了
4. Profile（表示名・自己紹介）を設定

**おすすめ初期設定**
- 2段階認証（2FA）を有効化
- SSHキーを登録（開発PCで使う場合）

---

# リポジトリ作成（GitHub Pages用）

- ユーザーページ用のリポジトリ名は **`<username>.github.io`**
- 例: `masakadop.github.io`

作成時の推奨:
- Public
- READMEあり
- mainブランチ

---
layout: section
---

# 2. Codex連携

---

# Codex CLIの準備

```bash
# 例: Codex CLIをインストール
npm i -g @openai/codex

# バージョン確認
codex --version
```

> インストール方法は利用環境で変わるため、公式手順を優先してください。

---

# GitHubと連携して開発する流れ

```bash
# リポジトリをclone
git clone https://github.com/<username>/<username>.github.io.git
cd <username>.github.io

# Codexを起動して作業
codex
```

Codexでやる代表例:
- HTML/CSS修正
- 記事やスライド生成
- コミットメッセージ作成補助

---
layout: section
---

# 3. Slidevで.mdからスライド作成

---

# Slidev最小構成

```bash
# プロジェクト直下で
npm init -y
npm i -D @slidev/cli

# slides.md を作成
npx slidev slides.md
```

- `slides.md` がスライド本体
- `---` でページ区切り
- Markdown中心で作れる

---

# GitHub Pages向けにビルド

```bash
# how-to-codex ディレクトリへ静的出力
npx slidev build slides.md --base /how-to-codex/ --out how-to-codex
```

- `--base` は公開先パスに合わせる
- 出力先 `how-to-codex/` をそのまま公開可能

---
layout: section
---

# 4. 公開とLink to Bio追加

---

# 公開URL

このリポジトリでは次のURLで公開:

## `https://masakadop.github.io/how-to-codex/`

Link to Bio (`index.html`) にボタン追加:

```html
<a class="link" href="https://masakadop.github.io/how-to-codex/">GitHub×Codex How To Slides</a>
```

---

# 更新運用（おすすめ）

- 手順変更が出たら `slides.md` を更新
- `npx slidev build ...` で再ビルド
- commit & push で反映

**公開後チェック**
- PC/スマホで表示確認
- リンク切れ確認
- Link to Bioから遷移確認

---
layout: center
class: text-center
---

# 完了 🎉

GitHub作成 → Codex連携 → Slidev公開 → Link to Bio導線化

`https://masakadop.github.io/how-to-codex/`
