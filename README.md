# chat-template.net システムREADME

最終更新: 2026-03-21
対象サーバー: `160.251.239.184`（184）
プロジェクトルート: `/var/www/chat-template.net`

---

## 1) このシステムは何か

`chat-template.net` は、**チャット系サービスのテンプレート構成**です。

主な構成:
- Web公開面 (`public/`)
- シグナリングサーバー (`signaling/`)
- セキュアチャット実装一式 (`secure-chat/`)

---

## 2) ディレクトリ構成

- `public/index.html`
  - ルート公開ページ
- `signaling/`
  - `src/server.ts`, `dist/server.js`
  - Node/TypeScriptベースのシグナリング実装
- `secure-chat/`
  - `backend/`（バックエンド）
  - `web/`（Vite系フロントエンド）
  - `docs/`（設計メモ）
- `docs/CHAT_SYSTEM_STATUS_2026-03-21.md`
  - 現況確認メモ

---

## 3) 運用の考え方（現時点）

- `signaling` と `secure-chat` は責務が異なるため、
  サービス単位で起動/監視を分離する
- 公開前に以下を固定化する:
  - 利用ポート
  - 環境変数
  - systemdユニット名
  - nginxリバースプロキシ先

---

## 4) 初期確認コマンド

```bash
# 全体確認
ls -la /var/www/chat-template.net

# signaling 主要ファイル
ls -la /var/www/chat-template.net/signaling

# secure-chat 主要ファイル
ls -la /var/www/chat-template.net/secure-chat
```

---

## 5) 次に整備すべき項目

1. 起動手順（dev/prod）
2. ポート定義と依存サービス
3. 障害時の切り分け手順
4. 監視対象（プロセス/HTTP/SSL）

---

## 6) 障害時初動

1. DNSと証明書期限を確認
2. web/signaling/backend のどこで失敗しているか切り分け
3. ログ（systemd / nginx / アプリ）を時系列で確認
4. 復旧後に再発防止を docs に記録
