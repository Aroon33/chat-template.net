# chat-template.net Status (2026-03-21)

対象プロジェクト:
- projectId: `proj-184-chat-template-net`
- rootDir: `/var/www/chat-template.net`
- domain: `https://chat-template.net`

---

## 1) ディレクトリ確認

確認時点の主要構成:
- `/var/www/chat-template.net/public`
- `/var/www/chat-template.net/secure-chat`
- `/var/www/chat-template.net/signaling`
- `/var/www/chat-template.net/README.md`

---

## 2) Markdown/ドキュメント状況

現時点で確認できるMD:
- `/var/www/chat-template.net/README.md`

現状はREADMEのみのため、運用用ドキュメントは未整備。

---

## 3) 最低限の運用ドキュメント整備提案

次に作ると良いファイル:
1. `docs/PROJECT_PROGRESS.md`
   - 進捗、完了条件、未着手
2. `docs/REPORTING_STANDARD.md`
   - 報告テンプレ、命名規則、更新頻度
3. `docs/OPS_NOTES.md`
   - 起動/再起動手順、環境変数、依存サービス
4. `docs/SECURITY_NOTES.md`
   - 権限、公開範囲、秘密情報の取り扱い

---

## 4) 次アクション（提案）

- `secure-chat` と `signaling` の責務を分離表で明記
- 起動コマンド/ポート/接続先の定義を `OPS_NOTES.md` に記載
- 日次/週次の報告運用を `REPORTING_STANDARD.md` で固定

---

作成メモ:
- 本ファイルは「現況確認の初期スナップショット」。
- 詳細仕様は今後の実装状況に合わせて追記する。
