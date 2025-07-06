# ✋ TryPick

**毎週土曜にQiitaから「ハンズオン」系記事を自動取得し、Web表示＋メール配信するアプリ。**  
ユーザーはその週の10件から1つを選び、週1の技術実践習慣をつくることができます。

---

## 🔧 技術構成

| 機能           | 技術 / サービス       | 補足 |
|----------------|------------------------|------|
| フロント       | Next.js                | Web UIを担当（ISRで高速表示） |
| バックエンド   | Golang（Gin）          | Qiita API取得、記事提供、メールトリガ |
| 定期ジョブ     | Railway Scheduled Jobs | 毎週土曜に自動実行（記事取得＆配信） |
| データベース   | PostgreSQL（Railway）  | 記事キャッシュ、履歴保存 |
| デプロイ       | Railway                | API＋DB＋ジョブを無料で一括管理 |
| コンテナ管理   | Docker Compose         | 開発と本番を統一構成 |
| メール送信     | SendGrid（+ sendgrid-go） | 月100通まで無料。APIキーで送信 |
| AIコーディング支援 | Cursor（GPT-4o連携） | 設計・実装・デバッグを高速化 |

---

## 📁 フォルダ構成

trypick/
├── frontend/ # Next.js フロントエンド
├── backend/ # Gin API（Golang）
├── scripts/ # Qiita取得・メール送信などのバッチ処理
├── docker-compose.yml # ローカル／本番共通のサービス定義
├── .env # APIキー・DB接続・SendGrid設定など
└── README.md # このファイル

