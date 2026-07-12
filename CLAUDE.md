# Moccoa Works Web サイト — AI アシスタンス ルール

## 言語

- ユーザーへの返答および思考途中のメッセージは、すべて日本語で書く。
- git commit message は英語で書く。
- サイトのコンテンツ（HTML 内のテキスト）は英語で書く。既存ページのトーンに合わせる。

## サイト概要

- Developer "Moccoa Works" の公式サイト。GitHub Pages でホスティング。
- 独自ドメイン: https://moccoaworks.com （`CNAME` ファイルで設定。**絶対に削除・変更しない**）
- main ブランチのルートから直接配信。ビルドステップなし（Jekyll 等は不使用）。
- push すると 1〜2 分程度で自動デプロイされる。

## ディレクトリ構成

```
index.html          # トップページ
style.css           # サイト全体の共通スタイル（これ 1 枚に集約する）
apps/index.html     # アプリ一覧
apps/caffio/        # Caffio 紹介ページ（index.html）と release notes（releases.html）
support/index.html  # サポート・連絡先
privacy/index.html  # プライバシーポリシー
CNAME               # 独自ドメイン設定（触らない）
```

## 更新ルール

- 新しいページを作るときは既存ページの HTML 構造（header / nav / footer）と `style.css` を再利用し、見た目の一貫性を保つ。
- ページ固有の `<style>` タグは追加せず、必要なら `style.css` にクラスを足す。
- 変更後は必ずローカルでファイルをブラウザ表示するかプレビューして確認してから commit する。
- commit / push はユーザーの確認を取ってから行う。

## Caffio release notes の更新手順

Caffio のソースは `/Users/mocotomo/Documents/Caffio`（別リポジトリ）。

1. ユーザーから新バージョンの内容を聞く。または Caffio リポジトリの
   直近の git log から変更点を要約して提案し、ユーザーに確認してもらう。
2. `apps/caffio/releases.html` の一覧の**先頭**に新バージョンのエントリを追加する。
   形式: バージョン番号・日付（YYYY-MM-DD）・変更点の箇条書き（英語、ユーザー向けの言葉で。
   内部リファクタリングは書かない）。
3. 既存エントリは削除・変更しない（履歴として残す）。
