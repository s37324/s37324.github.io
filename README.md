# アプリの公開ドキュメント

App Store などに載せるプライバシーポリシーを、アプリごとに置く静的サイトです。

**Gleam リポジトリの GitHub Pages は使いません。** Gleam は private のままです。
公開するのは、別の公開リポジトリ `s37324.github.io` だけです。

公開後の URL:

- 一覧: https://s37324.github.io/
- Gleam サポート: https://s37324.github.io/gleam/support.html
- Gleam プライバシーポリシー: https://s37324.github.io/gleam/privacy-policy.html
- GitHub 上の Gleam フォルダ: https://github.com/s37324/s37324.github.io/tree/main/gleam

## 構成

```
docs/
  index.html                 アプリ一覧
  assets/site.css            共通スタイル
  gleam/                     アプリごとのフォルダ
    index.html
    support.html
    privacy-policy.html
  _template/                 次のアプリ用ひな形
  privacy-policy.html        Gleam への転送（旧パス互換）
```

新しいアプリを足す手順:

1. `_template/` を `docs/<アプリの英名>/` にコピーする
2. `APP_NAME` と本文を書き換える
3. ルートの `index.html` の一覧にリンクを足す
4. 下の公開スクリプトをもう一度実行する

利用規約やサポートを足す場合も、同じアプリフォルダに `terms.html` などを置けます。

## 公開リポジトリを作る（手元で1回）

GitHub にログインした自分の Mac で、Gleam を clone したあと:

```bash
cd docs
./publish-public-repo.sh
```

スクリプトが行うこと:

1. 公開リポジトリ `s37324.github.io` を新規作成する（すでにあれば再利用）
2. この `docs/` の中身だけを、そのリポジトリのルートへ push する
3. GitHub Pages を `main` のルートから有効にする

作成ページから空リポジトリだけ先に作る場合: [s37324.github.io を Public で作る](https://github.com/new?name=s37324.github.io&visibility=public)

README は追加しないでください。作ったあと、同じスクリプトを実行すれば中身を push します。
