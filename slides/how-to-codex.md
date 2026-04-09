class: center, middle

# GitHubアカウント作成 → AIバイブコーディング連携
## → Link to BioでGitHub Pages公開

スマホだけでも進められる手順をこのスライド1本で。

対象: はじめての人向け

---

# 0. 全体像

---

# 今日やること（3ステップ）

1. **GitHubアカウントを作る**
2. **スマホからAIで修正案を作り、GitHubに反映する**
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

- メール認証を必ず完了してから進める
- 表示名・自己紹介・アイコンを設定して、公開プロフィールを整える

---

# リポジトリ作成（GitHub Pages用）

- ユーザーページ用のリポジトリ名は **`<username>.github.io`**
- 例: `masakadop.github.io`

作成時の推奨:

- Public
- READMEあり
- mainブランチ

---

# 2. スマホでAIバイブコーディング

---

# まず用意するアプリ（スマホ）

- **ブラウザ**（Safari / Chrome）
- **GitHubアプリ**（任意、ブラウザだけでも可）
- **AIチャットアプリ**（ChatGPT など）

> ここではCLIは使いません。スマホ中心の操作に絞ります。

---

# スマホでの実作業フロー

1. GitHubで対象ファイル（例: `slides/how-to-codex.md`）を開く
2. 変更したい内容をAIに日本語で依頼
3. AIが返した差分案をコピー
4. GitHubのWeb編集画面で貼り付けてCommit

**依頼テンプレ（そのまま使える）**

- 「この.mdを、初心者向けに3ステップで説明する構成に直して」
- 「CLI前提の説明を削除し、スマホ操作中心に書き換えて」
- 「見出しと箇条書き中心で、読みやすく整形して」

---

# 失敗しにくい運用ルール

- いきなり本番を書き換えず、まず1ファイルずつ修正
- 1コミット1変更（例: タイトル修正、手順修正）
- Commitメッセージは具体的に
  - 例: `docs: CLI前提を削除しスマホ手順に更新`

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

# 公開反映のしくみ（かんたん）

- `index.html` と `slides/` をGitHub Pagesで配信
- Markdownを更新してcommit/pushするだけで反映
- PC不要で、スマホからでも更新運用が可能

---

# 4. 公開とLink to Bio追加

---

# 公開URL

このリポジトリでは次のURLで公開:

## `https://masakadop.github.io/slides/how-to-codex/`

Link to Bio (`index.html`) には以下の導線を配置済み:

```html
<a class="link" href="https://masakadop.github.io/slides/how-to-codex/">GitHub×AI バイブコーディング How To (Slides)</a>
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

GitHub作成 → スマホAI編集 → remark.js表示 → Link to Bio導線化

`https://masakadop.github.io/slides/how-to-codex/`
