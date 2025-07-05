# スライドの墓場

## はじめに

mdで作ったスライド置き場です。MarpフレームワークでMarkdownからHTMLスライドを自動生成し、GitHub Pagesで公開しています。

## 機能

- **Marpスライド**: MarpフレームワークでMarkdownからスライドを作成
- **自動HTML変換**: GitHub ActionsでMarpスライドをHTMLに自動変換
- **GitHub Pages公開**: 変換されたHTMLファイルを自動的にGitHub Pagesで配信

## 使い方

1. `slides/marp/`ディレクトリに`.md`ファイルを作成
2. フロントマターで`marp: true`を設定してMarp形式で記述
3. `master`ブランチにプッシュすると自動的にHTMLに変換されてGitHub Pagesで公開

## スライド例

- [脱毛を試してみた話](slides/marp/datsumou.md)
- [マットレスを選ぶときに考えたこと](slides/marp/bed.md)
- [日常的な情報収集](slides/marp/johou.md)
- [スマートホーム](slides/marp/smarthome.md)

## アイデア

- 概念シフト
  - なんかおもしろうそうなので
  - 書くことや目を付けることで物の捉え方を変える
  - 考えずにものを言うテクニック的なやつは別だっけ？
