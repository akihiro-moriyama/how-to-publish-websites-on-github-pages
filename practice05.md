# 実践05. たった2つのファイルでサイト構築！MDwiki

## MDwikiとは



## ウェブサイト構築の最短手順

1. MDwiki（mdwiki.html）と最初の原稿(index.md)を用意する
1. mdwiki.htmlはindex.htmlにファイル名変更する
1. GitHubで、リモートリポジトリを新規作成する
1. GitHub Desktopで、リモートリポジトリを自分のPCに[Clone]する
1. GitHub Desktopで、index.htmlとindex.mdをリモートリポジトリに[Push]する
1. GitHubで、リモートリポジトリの設定[Setting>GitHub Pages>Sourse]を＜none＞から＜master branch＞に変更する
1. 数分待つとウェブサイトが公開される

## 他の方法との比較

### GitHub Pagesのマークダウン変換と比較

実はGitHub Pages自体にもマークダウン記法で書かれたウェブコンテンツをHTMLに変換して表示する機能があります。つまり「index.md」だけがあればウェブサイトとして成立します。

この方法の欠点は、ナビゲーションメニューバーが表示されないということです。

ウェブサイトとしてページ数を増やしていきたいのであればナビゲーションメニューバーは必須です。そしてナビゲーションメニューバーのためにHTMLとCSSを記述するのは時間と手間と技術知識が必要です。MDwikiはこの手間を大幅削減します。

### WordPressと比較

## (以後作成中)