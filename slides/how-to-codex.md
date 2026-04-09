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

> ゴール: `https://slides.deno.dev/html?url=https://masakadop.github.io/slides/how-to-codex.md` を公開し、プロフィールに導線を置く

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
- パスキー設定（スマホ利用時に便利）

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

# 3. slides.deno.devで.mdを表示

---

# slides.deno.devリンク構成

```html
https://slides.deno.dev/html?url=https://masakadop.github.io/slides/how-to-codex.md
```

- スライド本体は `how-to-codex.md`
- 区切りは `---`
- 表示は slides.deno.dev 側が行うため、GitHub Pages側のHTML実装は不要

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

## `https://slides.deno.dev/html?url=https://masakadop.github.io/slides/how-to-codex.md`

Link to Bio (`index.html`) には以下の導線を配置済み:

```html
<a class="link" href="https://slides.deno.dev/html?url=https://masakadop.github.io/slides/how-to-codex.md">GitHub×AI バイブコーディング How To (Slides)</a>
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

GitHub作成 → スマホAI編集 → slides.deno.dev表示 → Link to Bio導線化

`https://slides.deno.dev/html?url=https://masakadop.github.io/slides/how-to-codex.md`
