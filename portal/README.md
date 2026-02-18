# 🚀 Toshogu Dev Portal

モダンでおしゃれなKong Konnect Developer Portal実装

## 📋 概要

Toshogu Dev Portalは、Kong Konnectをベースにした、エンタープライズグレードのAPI開発者ポータルです。3つの主要API（Catalogue、Cart、Order）を提供し、開発者がAPIを簡単に検索、テスト、統合できる環境を提供します。

## ✨ 主な機能

### 🎨 モダンなデザイン

- **カラーテーマ**: Indigo/Deep Purpleのグラデーション
- **レスポンシブデザイン**: モバイルからデスクトップまで対応
- **アニメーション**: スムーズなトランジションとホバーエフェクト
- **カスタムコンポーネント**: カード、ボタン、アラートなど

### 📚 充実したコンテンツ

#### ホームページ
- インパクトのあるヒーローセクション
- 主要機能の紹介（カードグリッド）
- API一覧プレビュー
- クイックスタートガイド
- サポートリソース

#### Getting Startedガイド
- アカウント作成からAPI呼び出しまでのステップバイステップガイド
- コードサンプル（curl、JavaScript）
- トラブルシューティング
- ベストプラクティス

#### APIライフサイクルガイド
- ライフサイクルステージ（Beta、Stable、Deprecated、Sunset）
- セマンティックバージョニング（SemVer）
- バージョン管理戦略
- 変更通知プロセス

#### API利用ガイド
- 認証とAPI Key管理
- リクエストのベストプラクティス
- ページネーション、フィルタリング、ソート
- パフォーマンス最適化
- レート制限とエラーハンドリング

#### 利用規約とポリシー
- 利用規約
- プライバシーポリシー
- 知的財産権
- コンプライアンス（GDPR、CCPA、個人情報保護法）

### 🔐 セキュリティ

- API Key認証
- RBAC（ロールベースアクセス制御）対応
- 開発者承認ワークフロー
- アプリケーション承認ワークフロー

## 📁 プロジェクト構造

```
portal/
├── apis.yaml                 # API定義
├── portal.yaml              # ポータル設定
├── theme.yaml               # カスタムテーマ定義
├── custom-styles.css        # カスタムスタイルシート
├── auth-strategies.yaml     # 認証戦略
├── assets/                  # アセット
│   ├── logo.png
│   ├── favicon.png
│   └── hero-image.png
├── pages/                   # ページコンテンツ
│   ├── home.md             # ホームページ
│   ├── apis.md             # API一覧ページ
│   ├── getting-started.md  # Getting Startedページ（レガシー）
│   └── guides/             # ガイドページ
│       ├── getting-started.md  # Getting Startedガイド
│       ├── lifecycle.md        # APIライフサイクル
│       ├── usage.md           # API利用ガイド
│       └── regulation.md      # 利用規約とポリシー
├── snippets/               # 再利用可能なスニペット
│   ├── toshogu-page-nav.md
│   └── sidebar.md
├── apis/                   # OpenAPI仕様
│   ├── catalogue/
│   │   └── openapi.yaml
│   ├── cart/
│   │   └── openapi.yaml
│   └── order/
│       └── openapi.yaml
└── docs/                   # APIドキュメント
    ├── catalogue_ja.md
    ├── cart_ja.md
    └── order_ja.md
```

## 🎨 デザインシステム

### カラーパレット

- **Primary**: Indigo (#3F51B5)
- **Secondary**: Deep Purple (#673AB7)
- **Success**: Green (#4CAF50)
- **Warning**: Orange (#FF9800)
- **Error**: Red (#F44336)
- **Info**: Blue (#2196F3)

### タイポグラフィ

- **フォントファミリー**: Inter, -apple-system, BlinkMacSystemFont
- **モノスペース**: Fira Code, Monaco, Menlo, Consolas
- **フォントサイズ**: 12px - 72px（レスポンシブ）
- **フォントウェイト**: 300 - 800

### スペーシング

- **XS**: 4px
- **SM**: 8px
- **MD**: 16px
- **LG**: 24px
- **XL**: 32px
- **2XL - 5XL**: 48px - 128px

### コンポーネント

#### ボタン
- Primary: グラデーション背景、白テキスト
- Secondary: 透明背景、ボーダー、プライマリカラーテキスト
- ホバーエフェクト: 上昇アニメーション、シャドウ強化

#### カード
- 白背景、丸角（1rem）
- 軽いシャドウ
- ホバー時: 上昇アニメーション、シャドウ強化、ボーダーカラー変更

#### アラート
- 4種類: Info、Success、Warning、Error
- グラデーション背景
- 左ボーダーアクセント

## 🚀 デプロイ

### Kong Konnectへのデプロイ

```bash
# kongctlを使用してデプロイ
kongctl apply -f portal.yaml
kongctl apply -f apis.yaml
kongctl apply -f theme.yaml
kongctl apply -f auth-strategies.yaml
```

### ローカル開発

Kong Dev Portalのローカル開発環境をセットアップ:

```bash
# Kong Konnectダッシュボードでプレビュー
# 1. portal/ディレクトリ内のファイルをアップロード
# 2. ポータルエディターでプレビュー
# 3. 変更を保存して公開
```

## 📝 カスタマイズ

### テーマのカスタマイズ

[theme.yaml](theme.yaml)を編集してカラー、タイポグラフィ、スペーシングをカスタマイズ:

```yaml
colors:
  primary:
    base: "#YOUR_COLOR"
    light: "#YOUR_LIGHT_COLOR"
    dark: "#YOUR_DARK_COLOR"
```

### スタイルのカスタマイズ

[custom-styles.css](custom-styles.css)を編集してカスタムCSSを追加:

```css
.your-custom-class {
  /* カスタムスタイル */
}
```

### コンテンツのカスタマイズ

`pages/`ディレクトリ内のMarkdownファイルを編集してコンテンツを更新:

```markdown
# ページタイトル

コンテンツ...

::card
---
title: "カードタイトル"
---
カード内容
::
```

## 🔧 MDCコンポーネント

Kong Dev Portalで使用可能な主なMDCコンポーネント:

### レイアウト

- `::page-section` - ページセクション
- `::page-hero` - ヒーローセクション
- `::card-grid` - カードグリッド

### コンポーネント

- `::card` - カード
- `::button` - ボタン
- `::alert` - アラート
- `::accordion` - アコーディオン
- `::tabs` - タブ
- `::page-navigation` - ページナビゲーション

### 使用例

```markdown
::card
---
title: "カードタイトル"
---
カード内容
::

::button
---
appearance: "primary"
size: "large"
to: "/path"
---
ボタンテキスト
::

::alert
---
appearance: "info"
---
アラートメッセージ
::
```

## 📚 参考リンク

- [Kong Konnect Developer Portal Docs](https://portaldocs.konghq.com/)
- [Kong Dev Portal Documentation](https://developer.konghq.com/dev-portal/)
- [MDC (Markdown Components)](https://portaldocs.konghq.com/)

## 🤝 コントリビューション

改善提案やバグ報告は、以下の方法で受け付けています:

1. Issueを作成
2. プルリクエストを送信
3. [support@toshogu.example.com](mailto:support@toshogu.example.com)へ連絡

## 📄 ライセンス

このプロジェクトは社内利用を目的としています。

## 📞 サポート

- **一般お問い合わせ**: [support@toshogu.example.com](mailto:support@toshogu.example.com)
- **セキュリティ**: [security@toshogu.example.com](mailto:security@toshogu.example.com)
- **プライバシー**: [privacy@toshogu.example.com](mailto:privacy@toshogu.example.com)

---

**最終更新**: 2026年2月14日
**バージョン**: 1.0.0
