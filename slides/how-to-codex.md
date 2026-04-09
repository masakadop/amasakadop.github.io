class: center, middle

# GitHubアカウント作成 → Codex連携
## → Link to BioでGitHub Pages公開

手順をこのスライド1本で。

対象: はじめての人向け

---

# 0. 全体像

---

# 今日やること（3ステップ）

1. **GitHubアカウントを作る**
2. **Codex (CLI) をGitHubと連携する**
3. **GitHub Pagesで公開してLink to Bioに追加**

> ゴール: `https://masakadop.github.io/slides/how-to-codex/` を公開し、プロフィールに導線を置く

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

# 3. remark.jsで.mdをリアルタイム表示

---

# remark.js最小構成

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/remark/0.15.0/remark.min.js"></script>
<script>
  remark.create({ source: markdownText })
</script>
```

- スライド本体は `how-to-codex.md`
- 区切りは `---`
- 事前ビルド不要で、GitHub Pages上でそのまま表示可能

---

# GitHub Actionsでの事前生成を削減

- Slidevビルドを実行しないため、Node.jsセットアップが不要
- `index.html` と `slides/` ディレクトリをそのままPagesへ配置
- Markdownを更新してpushするだけで反映

---

# 4. 公開とLink to Bio追加

---

# 公開URL

このリポジトリでは次のURLで公開:

## `https://masakadop.github.io/slides/how-to-codex/`

Link to Bio (`index.html`) には以下の導線を配置済み:

```html
<a class="link" href="https://masakadop.github.io/slides/how-to-codex/">GitHub×Codex How To (Slides)</a>
```

---

# 更新運用（おすすめ）

- 手順変更が出たら `slides/how-to-codex.md` を更新
- commit & push で反映

**公開後チェック**

- PC/スマホで表示確認
- リンク切れ確認
- Link to Bioから遷移確認

---

class: center, middle

# 完了 🎉

GitHub作成 → Codex連携 → remark.js表示 → Link to Bio導線化

`https://masakadop.github.io/slides/how-to-codex/`
