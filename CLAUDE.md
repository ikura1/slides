# CLAUDE.md

このファイルは、Claude Code (claude.ai/code) がこのリポジトリで作業する際のガイダンスを提供します。

## リポジトリ概要

日本語で作成されたプレゼンテーション資料を管理する個人スライドリポジトリです。Marpフレームワークをメインとして使用し、GitHub ActionsでHTMLに自動変換してGitHub Pagesで配信しています。

- **Marpスライド** (`slides/marp/`内): MarpフレームワークとYAMLフロントマターを使用
- **その他のスライド** (`slides/`内): その他のMarkdownファイル
- **自動HTML変換**: GitHub ActionsでMarpスライドをHTMLに変換
- **GitHub Pages配信**: 変換されたHTMLファイルを自動的にGitHub Pagesで公開

## Marpスライドフレームワーク

### 基本設定
- フロントマターで`marp: true`を使用
- サポートテーマ: `default`, `gaia`
- 標準設定: `paginate: true`, `backgroundColor: #ffffff`
- 例: `slides/marp/datsumou.md`

### スライド作成ルール
- スライド区切り: `---`
- 画像挿入: `![bg right:30% w:300](image.png)`
- テーブル: Markdown記法に対応
- 特殊記法: Marp独自の記法を使用可能

## 自動デプロイ

Marpスライドの自動HTML変換とGitHub Pages配信システム：
- `master`ブランチへのプッシュで自動トリガー
- GitHub Actionsワークフロー (`.github/workflows/pages.yml`) がMarpスライドをHTMLに変換
- Marp設定ファイル (`.marprc.yml`) で変換オプションを管理
- 変換されたHTMLファイルを`output`ディレクトリに出力
- GitHub PagesでHTMLファイルを自動公開

## ファイル構造

```
slides/
├── slides/
│   ├── marp/            # Marpスライド (メイン)
│   │   ├── bed.md
│   │   ├── datsumou.md
│   │   ├── johou.md
│   │   └── smarthome.md
│   ├── exercise.md      # その他のスライド
│   ├── input_data.md
│   └── talk.md
├── .marprc.yml          # Marp設定ファイル
├── .github/workflows/pages.yml  # GitHub Actions設定
├── template.md          # Reveal.jsスライドテンプレート (レガシー)
├── index.html           # シンプルなランディングページ
└── README.md           # リポジトリドキュメント
```

## スライド作成ワークフロー

新しいMarpスライドを作成する場合：
1. `slides/marp/`ディレクトリに`.md`ファイルを作成
2. フロントマターで`marp: true`を設定
3. `slides/marp/datsumou.md`のフロントマターパターンを参考にする
4. `master`ブランチにプッシュすると自動的にHTMLに変換されてGitHub Pagesで公開

## ローカルでのスライド表示

- **Marp CLIでのプレビュー**: `marp --preview slides/your-slide.md`
- **VS Code拡張機能**: Marp for VS Codeでリアルタイムプレビュー
- **GitHub Pages**: プッシュ後に自動生成されたHTMLファイルをオンラインで確認

## 言語について

すべてのスライドコンテンツは日本語で作成されています。このリポジトリは個人プレゼンテーションアーカイブ（「スライドの墓場」）として機能します。