# futariseikatsu-legal

iOS アプリ「ふたりせいかつ」（FutariSeikatsu）の法的情報
（プライバシーポリシー / 利用規約 / 特定商取引法に基づく表記）を
GitHub Pages で公開するための静的サイト。

## 公開 URL

ベース URL: `https://mon50.github.io/futariseikatsu-legal/`

| ドキュメント | ja | en |
|---|---|---|
| プライバシーポリシー | `/legal/privacy/ja/` | `/legal/privacy/en/` |
| 利用規約 | `/legal/terms/ja/` | `/legal/terms/en/` |
| 特定商取引法に基づく表記 | `/legal/tokushoho/ja/` | `/legal/tokushoho/en/` |

App Store Connect / アプリ内の設定画面からは、上記のフル URL
（例: `https://mon50.github.io/futariseikatsu-legal/legal/privacy/ja/`）を参照する。

## 構成

```
index.html                     各ページへのリンク集
legal/shared/style.css         全ページ共通スタイル
legal/<doc>/<lang>/index.html  各文書（doc: privacy | terms | tokushoho, lang: ja | en）
.nojekyll                      GitHub Pages の Jekyll 処理を無効化
```

日本語版が正本。英語版は日本語版のミラーであり、齟齬がある場合は日本語版が優先する旨を
各ページに明記している。

## 記載内容の前提

本サイトの記述は、アプリ本体リポジトリ `futariseikatsu-ios` の実装に対応している。
以下を変更した場合は、本サイトの該当箇所も更新すること。

- Supabase のスキーマ（保存する項目・テーブル）
- サブスクリプションのプラン構成・提供範囲（現在は「どちらか一方の契約でふたりとも利用可」）
- 第三者処理者の追加・変更（現在は Supabase, Inc. と Apple Inc. のみ）
- プッシュ通知、写真添付など、新たに端末の機能・データを扱う機能の追加
- アカウント削除の挙動（`delete-user` Edge Function および `delete_user_data` RPC）

## 更新手順

1. 該当する `legal/<doc>/<lang>/index.html` を編集する。ja / en の両方を揃えること。
2. ページ上部の「最終更新日」と、末尾の「改訂履歴」に変更内容を追記する。
3. コミットして push する（GitHub Pages が自動で反映する）。

> **注意**: 公開前に各文書内の `<<CONTACT_EMAIL>>` を実際の連絡先メールアドレスへ置換すること。
> 現時点では全ページでプレースホルダのままにしてある。
