# チーム開発体験プロジェクト - Issue一覧

## Issue #1: 環境構築（First commit）
**担当者**: プロジェクトリーダー  
**優先度**: 高  
**ラベル**: `setup`, `documentation`

### 内容
- [ ] リポジトリの初期化
- [ ] 基本的なHTMLファイルの作成
  - `index.html` (ホームページ)
  - `team.html` (チーム紹介ページ)
  - `contact.html` (お問い合わせフォーム)
- [ ] 共通CSSファイル `main.css` の作成
- [ ] `README.md` の作成
- [ ] 初回コミットの実行

### 完了条件
- 基本的なウェブサイトが動作すること
- 全ページが共通CSSでスタイリングされていること
- ナビゲーションが正常に動作すること

---

## Issue #2: チームメンバー情報の更新（改修）
**担当者**: 全員  
**優先度**: 中  
**ラベル**: `content`, `update`

### 内容
現在の仮名を実際の参加者名に変更する：

#### 田中太郎 → 山田太郎
- プロジェクトリーダー / フロントエンド開発
- 担当ファイル: `team.html` の1番目のメンバー情報

#### 佐藤花子 → 佐々木美咲
- デザイナー / UI/UX設計
- 担当ファイル: `team.html` の2番目のメンバー情報

#### 鈴木次郎 → 田中健太
- バックエンド開発
- 担当ファイル: `team.html` の3番目のメンバー情報

#### 高橋美咲 → 伊藤愛
- テスター / 品質保証
- 担当ファイル: `team.html` の4番目のメンバー情報

### 完了条件
- 全メンバーの名前が実際の参加者名に変更されていること
- 各担当者の役割が明確に記載されていること

---

## Issue #3: ナビゲーションメニューの改修（コンフリクト修正）
**担当者**: 複数人  
**優先度**: 中  
**ラベル**: `feature`, `conflict`

### 内容
各担当者が同時に異なるナビゲーションメニューの改修を行う：

#### 担当者A: ナビゲーションリンクの追加
- `index.html`, `team.html`, `contact.html` の `<nav>` セクションに新しいリンクを追加
- 追加するリンク: `<a href="about.html">About</a>`

#### 担当者B: ナビゲーションのスタイル変更
- `main.css` の `nav a` スタイルを変更
- 背景色を `#333` から `#2c3e50` に変更
- ホバー時の背景色を `#555` から `#34495e` に変更

#### 担当者C: ナビゲーション構造の変更
- `index.html`, `team.html`, `contact.html` の `<nav>` セクションの構造を変更
- `<nav>` を `<header>` 内に移動
- 新しい構造:
```html
<header>
    <nav>
        <!-- 既存のリンク -->
    </nav>
</header>
```

### 予想されるコンフリクト
1. **ファイル構造の競合**: 担当者Cが `<header>` タグを追加する一方で、担当者Aが既存の `<nav>` に直接リンクを追加
2. **CSS競合**: 担当者Bが `nav a` のスタイルを変更する一方で、担当者Cが新しい構造を追加
3. **同時編集**: 3つのファイル（`index.html`, `team.html`, `contact.html`）を複数人が同時に編集

### 解決方法
1. 各担当者が異なるブランチで作業
2. プルリクエストを作成してレビュー
3. コンフリクトが発生した場合は手動でマージ
4. 最終的に統合してマージ

### 完了条件
- ナビゲーションメニューが正常に動作すること
- 新しいリンクが追加されていること
- スタイルが統一されていること
- コンフリクトが適切に解決されていること

---

## 作業手順

### 1. 環境構築
```bash
git clone [リポジトリURL]
cd team-development
git checkout -b setup/initial-commit
# ファイル作成・編集
git add .
git commit -m "Initial commit: 基本的なウェブサイトの作成"
git push origin setup/initial-commit
```

### 2. チームメンバー情報更新
```bash
git checkout main
git pull origin main
git checkout -b feature/update-team-members
# 各担当者が自分の担当部分を編集
git add .
git commit -m "Update team member names"
git push origin feature/update-team-members
```

### 3. ナビゲーション改修（コンフリクト体験）
```bash
# 担当者A
git checkout -b feature/add-navigation-link
# ナビゲーションリンクを追加

# 担当者B  
git checkout -b feature/update-navigation-style
# CSSスタイルを変更

# 担当者C
git checkout -b feature/restructure-navigation
# ナビゲーション構造を変更
```

各ブランチで作業後、プルリクエストを作成してコンフリクトを体験・解決する。 