# 薬局コミュニケーション

薬局での受付、症状、安全確認、薬の説明、理解確認を、指差しと文字で支援する静的Webツールです。GitHub Pagesでそのまま公開できる構成にしています。

## ファイル構成

- `index.html` — 本体
- `404.html` — GitHub Pages用404ページ
- `og-image.png` — OGP / Twitter Card画像（1200×630）
- `favicon.svg` — モダンブラウザ用favicon
- `favicon.ico` — 互換用favicon
- `favicon-32x32.png` — PNG favicon
- `apple-touch-icon.png` — iPhone / iPad用アイコン
- `icon-192.png` / `icon-512.png` — Web App Manifest用アイコン
- `site.webmanifest` — Web App Manifest
- `.nojekyll` — GitHub PagesでJekyll処理を行わないためのファイル

## GitHub Pagesで公開する

1. このフォルダの中身をGitHubリポジトリのルートに置く。
2. GitHubの **Settings → Pages** を開く。
3. **Deploy from a branch** を選び、`main` / `/(root)` を指定する。
4. 公開URLが発行されたらブラウザで動作を確認する。

## OGPで最後に設定する項目

`index.html`にはOGP・Twitter Cardの基本設定を入れています。`og-image.png`は1200×630です。

GitHub Pagesの公開URLが確定したら、SNSクローラーへの互換性を最大化するため、`<head>`に次の3項目を追加することを推奨します。

```html
<link rel="canonical" href="https://YOUR-ACCOUNT.github.io/YOUR-REPOSITORY/">
<meta property="og:url" content="https://YOUR-ACCOUNT.github.io/YOUR-REPOSITORY/">
<meta property="og:image" content="https://YOUR-ACCOUNT.github.io/YOUR-REPOSITORY/og-image.png">
```

現在の`og:image`は相対URLでもサイト内では参照できますが、SNSサービスによっては絶対URLの方が確実です。公開URLが決まった時点で差し替えてください。

## プライバシー

本版では `fetch`、`XMLHttpRequest`、`localStorage`、`sessionStorage` を利用せず、入力内容をサーバーへ保存・送信する機能を実装していません。共有端末では利用後に「内容を消去」してからページを閉じてください。

## 注意

このツールはコミュニケーション補助を目的とするもので、診断や緊急時対応を代替するものではありません。
