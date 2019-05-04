# 実践05. たった2つのファイルでサイト構築！MDwiki

## MDwikiとは

![MDwiki公式サイト](img/mdwiki-website-1440x480.png)

note: http://dynalon.github.io/MDwiki/

[MDwiki<i class="fas fa-external-link-alt"></i>](http://dynalon.github.io/MDwiki/)は、「CMS(コンテンツ・マネジメント・システム)」と呼ばれるウェブアプリケーションです。

MDwikiの最大の特徴は、CMSを構成するファイルがHTMLファイルひとつしかないということです。非常にシンプルでコンパクトなCMSではありますが、その代わり多機能ではありません。マークダウン記法で書かれたウェブコンテンツをHTMLに変換する以外は他に目立った機能がほとんどないという変わり種のCMSです。

なお、当サイトもMDwikiで構築されています。

## MDwikiの最小構成

最低限2つのファイルをウェブサーバー上に置けばMDwikiは動作します。サーバーアプリケーションにありがちなコマンドラインを用いたインストールは必要ありません。

### 例

###### 1. ウェブサーバー内のファイルの配置

```
(http://www.example.com/)
├ index.html　　←MDwiki本体
└ index.md　　　←ウェブコンテンツ
```

###### 2. ウェブブラウザのURL欄への入力

```
http://www.example.com/
```

###### 3. MDwikiによって転送される先のURL

```
http://www.example.com/#!index.md
```

## ウェブサイト構築の最短手順

以下に[GitHub Pages<i class="fas fa-external-link-alt"></i>](https://pages.github.com/)と[MDwiki<i class="fas fa-external-link-alt"></i>](http://dynalon.github.io/MDwiki/)を用いてのウェブサイト構築の最短手順を示します。この作業の前提として**GitおよびGitHubの使い方を既に理解している**必要があります。

### 手順

1. MDwiki（mdwiki.html）と最初の原稿(index.md)を用意する
1. mdwiki.htmlをindex.htmlにファイル名変更する
1. GitHubで、リモートリポジトリを新規作成する
1. GitHub Desktopで、リモートリポジトリを自分のPCに[Clone]する
1. GitHub Desktopで、index.htmlとindex.mdをリモートリポジトリに[Push]する
1. GitHubで、リモートリポジトリの設定[Setting>GitHub Pages>Theme Chooser]で、一つテーマを選ぶ
1. GitHubで、リモートリポジトリの設定[Setting>GitHub Pages>Sourse]を＜none＞から＜master branch＞に変更する
1. 完了。数分待つとウェブサイトが公開される

## 他の方法との比較

ウェブサイトを構築するには複数の方法があり、それぞれ長所と短所があります。

### WordPressとの比較

[WordPress<i class="fas fa-external-link-alt"></i>](https://wordpress.org/)は、「CMS(コンテンツ・マネジメント・システム)」と呼ばれるウェブアプリケーションです。ユーザーが編集者アカウントでWordPressにログインしてコンテンツを投稿すると、WordPressがそれをHTMLに変換してウェブサイトとして公開する仕組みです。

この方法の難点

* WordPressはGitHub Pages上で動作しない
* WordPressは多機能であるため覚えなければならないことが多い

MDwikiとの比較

* MDwikiはGitHub Pages上で動作する
* MDwikiはシンプル単機能であるため少数の約束事だけ覚えれば良い

### GitHub Pagesのマークダウン対応との比較

[GitHub Pages<i class="fas fa-external-link-alt"></i>](https://pages.github.com/)自体にもマークダウン記法で書かれたウェブコンテンツをHTMLに変換して表示する機能があります。つまり「index.md」だけがあればウェブサイトとして成立します。

この方法の難点

* GitHub Pagesのマークダウン対応機能ではナビゲーションメニューバーが表示されない
* ウェブサイトとしてページ数を増やしていきたいのであればナビゲーションメニューバーは必須
* ナビゲーションメニューバーのためにHTMLとCSSを記述するのは時間と手間と技術知識が必要

MDwikiとの比較

* MDwikiは、マークダウン記法で書かれたナビゲーションメニューバーをHTML化する機能がある(自動生成はしない)

### GitHub社の推奨するJekyllとの比較

[Jekyll<i class="fas fa-external-link-alt"></i>](http://jekyllrb-ja.github.io/)は、「静的サイトジェネレーター」と呼ばれるアプリケーションです。マークダウン記法でウェブコンテンツを作成すると、ウェブコンテンツをHTML化し、目次やナビゲーションメニューバーやその他のパーツを自動的に生成・更新してくれます。[GitHub社ではGitHub Pages上でブログを運営するためのツールとして「Jekyll」を推奨しています](https://help.github.com/en/articles/using-jekyll-as-a-static-site-generator-with-github-pages)。

この方法の難点

* Jekyllはコマンドライン式アプリケーションであり素人には扱えない
* JekyllはWindows上で動作しない

MDwikiとの比較

* MDwikiは、本体である「mdwiki.html」ファイルをウェブサーバー上に置くだけでインストールが完了する
* MDwikiは、マークダウン記法で書かれたナビゲーションメニューバーをHTML化する機能がある(自動生成はしない)

## MDwikiの短所

### GUIがない

WordPressのようなメジャーなCMSの大多数は、ユーザーが編集者アカウントでWordPressにログインしてコンテンツを投稿すると、CMSがそれをHTMLに変換してウェブサイトとして公開する仕組みです。

他方、MDwikiはGUIが一切ありません。マークダウン記法で書かれたウェブコンテンツをウェブサーバー上のMDwiki(mdwiki.html)と同じフォルダに置くことで、投稿と見なされます。

### 最新投稿一覧を自動生成しない

WordPressのようなメジャーなCMSの大多数は、ユーザーがコンテンツを投稿すると、CMSがそれに応じて目次や最新投稿一覧を自動生成または自動更新してくれます。

他方、MDwikiはそのような便利な機能は一切ありません。ナビゲーションメニューをマークダウン記法で書くとHTMLに変換してくれる機能があるだけです。ブログのような毎日投稿を行う運用では苦痛を感じることでしょう。

### ページ読込時に一瞬レイアウトが崩れる

MDwikiのウェブコンテンツは、ウェブブラウザから読み込まれる毎に都度HTMLに変換されます。PCの性能によってはこの変換処理に時間がかかり、ページ読込時に一瞬レイアウトが崩れて見えます。一瞬のこととはいえ、他のCMSでは発生しないことなので気になります。

### サイト内検索ができない

MDwikiに検索機能はありません。どうしてもという場合はGoogleの検索オプション`site:`に頼ることになります。

> **特定のサイトを検索する**
>
> サイトまたはドメインの前に「`site:`」を付けます。例: `site:youtube.com` または `site:.gov`
> ( https://support.google.com/websearch/answer/2466433 より引用)

## 関連ページ

###### 関連ページ

* [01. なにが違うの？GitとGitHub](practice01.md)
* [02. コマンドラインはもう不要・GitHub Desktop](practice02.md)
* [03. 完全無料のウェブサーバー・GitHub Pages](practice03.md)
* [04. これだけ知ればGitHub Pageを使える！Git用語](practice04.md)
* <i class="far fa-hand-point-right fa-fw"></i>05. たった2つのファイルでサイト構築・MDwiki
* [06. 圧倒的な作業の効率化！マークダウン記法](practice06.md)
* [07. 真にミニマルなマークダウンエディタ・Typora](practice07.md)
* [08. Git対応高機能テキストエディタ・ATOM](practice08.md)
* [09. MDwikiをカスタマイズする・基本編](practice09.md)
* [10. MDwikiをカスタマイズする・HTML編](practice10.md)
* [11. MDwikiをカスタマイズする・CSS編](practice11.md)
* [12. 弱点克服！MDwikiをGoogle検索の対象にする](practice12.md)