---
layout: default
title: GitHub Pages ハウツー（初心者向け）
---

# GitHub Pages ハウツー（初心者向け）

この手順書では、次の 2 点を順番に実施します。

1. GitHub Pages を公開する
2. 公開済みリポジトリの `index.html` を GitHub Copilot で編集し、テトリスを作る

> 想定: このリポジトリでは `index.md` を Jekyll で変換して公開します。

---

## 0. 事前準備

- GitHub アカウントを用意する
- ブラウザで GitHub にログインする
- VS Code をインストールし、GitHub Copilot 拡張を有効化する

---

## 1. GitHub Pages を公開する（`index.md` + Jekyll）

### 手順 1-1. 公開用リポジトリを作る

1. GitHub で新規リポジトリを作成
2. リポジトリ名を `＜ユーザー名＞.github.io` にする
   - 例: ユーザー名が `octocat` なら `octocat.github.io`
3. Public で作成する

### 手順 1-2. `index.md` を作成する

リポジトリ直下に `index.md` を作り、以下のように書きます。

```md
---
layout: default
title: はじめての GitHub Pages
---

# はじめての GitHub Pages

GitHub Pages の公開に成功しました。
```

ポイント:

- 先頭の `---` で囲んだ部分は **Front Matter**（Jekyll の設定）
- `index.md` は公開時に HTML に変換され、トップページとして表示されます

### 手順 1-3. GitHub Pages を有効化する

1. リポジトリの **Settings** を開く
2. 左メニューの **Pages** を開く
3. **Build and deployment** の **Source** を `Deploy from a branch` にする
4. Branch を `main`、フォルダを `/ (root)` に設定して Save

### 手順 1-4. 公開URLを確認する

数分待ってから次の URL にアクセス:

- `https://＜ユーザー名＞.github.io/`

`index.md` の内容が表示されれば公開完了です。

---

## 2. GitHub Copilot で `index.html` を編集してテトリスを作る

> ここでは「公開サイトの説明ページ（`index.md`）」とは別に、実装練習として `index.html` を Copilot で編集します。

### 手順 2-1. ローカルにクローンして VS Code で開く

```bash
git clone https://github.com/＜ユーザー名＞/＜リポジトリ名＞.git
cd ＜リポジトリ名＞
code .
```

### 手順 2-2. `index.html` の土台を用意する

`index.html` に以下の最小構成を書きます。

```html
<!doctype html>
<html lang="ja">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Tetris</title>
    <style>
      body { display: grid; place-items: center; min-height: 100vh; margin: 0; }
      canvas { border: 2px solid #333; }
    </style>
  </head>
  <body>
    <canvas id="game" width="300" height="600"></canvas>
    <script src="./tetris.js"></script>
  </body>
</html>
```

### 手順 2-3. Copilot に `tetris.js` を作らせる

1. 新規ファイル `tetris.js` を作成
2. 先頭にコメントで要件を書く
3. Copilot Chat またはインライン補完で生成

Copilot への指示例（そのまま貼り付け可）:

```txt
HTML5 Canvas で動くシンプルなテトリスを JavaScript で実装してください。
要件:
- 10x20 グリッド
- 7種類のテトロミノ
- 左右移動、回転、ソフトドロップ
- ライン消去とスコア表示
- ゲームオーバー判定
- 外部ライブラリは使わない
- 初心者が読めるように、関数ごとに日本語コメントを入れる
```

### 手順 2-4. Copilot で改善を繰り返す

不具合が出たら、エラー文をそのまま Copilot に渡して修正します。

指示例:

- `回転時に壁へめり込むので wall kick を簡易実装して` 
- `スコアを右上に表示して` 
- `ゲームオーバー時に Enter キーでリスタートできるようにして`

### 手順 2-5. 動作確認して公開へ反映

1. ブラウザで `index.html` を開いて動作確認
2. 問題なければコミットして push

```bash
git add index.html tetris.js
git commit -m "Add Tetris implementation with Copilot"
git push origin main
```

---

## 3. 運用のコツ（初心者向け）

- まずは「動く最小版」を作る
- 次に Copilot へ 1 指示ずつ依頼する（大きな要求を一度に出さない）
- 変更ごとにコミットして戻せる状態を保つ
- 公開 URL で最終表示を必ず確認する

---

## 4. つまずきポイント

- **Pages が表示されない**: `Settings > Pages` の branch 設定を再確認
- **反映が遅い**: push 後 1〜5 分程度待って再読込
- **Jekyll エラー**: `index.md` の Front Matter (`---`) の閉じ忘れを確認
- **ゲームが動かない**: ブラウザ開発者ツールの Console のエラーを Copilot に貼って修正
