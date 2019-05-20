# 実践12. 弱点克服！MDwikiをGoogle検索の対象にする

## MDwikiで作ったサイトを検索で見つけられない理由

MDwikiで作ったサイトは基本的には検索で見つけることができません。これにはいくつかの理由があります。

### 理由1：ウェブサイト運営者がGoogleにウェブサイトを登録していない

Googleやbingなどの検索サービスは、ロボットと呼ばれる自動プログラムによって常にインターネット上に新しいウェブサイトが開設されていないか探しています。しかしウェブサイト数の爆発的に増えた現代において、偶然ロボットに発見してもらえることを期待することは宝くじの1等当選を期待するようなものです。ウェブサイト運営者が自発的にGoogleやbingにウェブサイトのURLを登録する必要があります。

### 理由2：sitemap.xmlがない

Googleやbingにウェブサイト内のすべてのページを登録するには「sitemap.xml」が必要です。sitemap.xmlとは、Googleやbingなどの検索サービスにウェブサイトのページ構成を知らせるためのページURL一覧表です。しかしながら、MDwikiはsitemap.xmlを自動生成しないため、ウェブサイトのURLだけしか(ページとしてはindex.htmlだけしか)登録できません。

### 理由3：Googleにおける「#!」を含むURLの扱い
ウェブページのURLが文字列`#!`を含む場合、GoogleはURLの当該箇所を`?_escaped_fragment_=`に置き換えてからそのウェブページが実在するかどうかを確認しに行きます。MDwiki側ではそのようなURLを求められた場合、`?_escaped_fragment_=`以降の文字列はなかったものとしてページを表示します。よって、たとえsitemap.xmlがあったとしても、MDwikiで構築されたウェブサイトでGoogle検索の対象となるのはウェブサイトのURLだけ(ページとしてはindex.htmlだけ)になります。

## 対策

いまのところ対策としてできるのは２つです。

1. Googleサーチコンソールで手作業でURLを登録する
1. 表紙(index.md)に各ページの概要に相当する文書を書く

### GoogleサーチコンソールでURLを登録する

** 手順 **

1. Googleサーチコンソールを開く <https://search.google.com/search-console/about?hl=ja>
1. (初回利用時であればここでURL入力欄が開く)
1. サイトのURLを入力
1. [プロパティを追加]ボタンクリック
1. 所有権の確認画面よりファイル名が長い乱数になっているHTMLファイルをダウンロードする
1. ダウンロードしたHTMLファイルをウェブサーバー上のindex.html(mdwiki.htmlをリネームしたもの)と同じ階層に配置する

### 表紙(index.md)に各ページの概要に相当する文書を書く

非常にローテクな手段ですが、index.mdに各ページの概要(description)に相当する文書を書くことで、サイト全体の概要をGoogleに伝えることができます。最低でも全ページのタイトルを書きましょう。

## OGPを設定する

## （以後作成中）

## 関連ページ

###### 関連ページ

* [01. なにが違うの？GitとGitHub](practice01.md)
* [02. コマンドラインはもう不要・GitHub Desktop](practice02.md)
* [03. 完全無料のウェブサーバー・GitHub Pages](practice03.md)
* [04. これだけ知ればGitHub Pageを使える！Git用語](practice04.md)
* [05. たった2つのファイルでサイト構築・MDwiki](practice05.md)
* [06. 圧倒的な作業の効率化！マークダウン記法](practice06.md)
* [07. 真にミニマルなマークダウンエディタ・Typora](practice07.md)
* [08. Git対応高機能テキストエディタ・ATOM](practice08.md)
* [09. MDwikiをカスタマイズする・基本編](practice09.md)
* [10. MDwikiをカスタマイズする・HTML編](practice10.md)
* [11. MDwikiをカスタマイズする・CSS編](practice11.md)
* <i class="far fa-hand-point-right fa-fw"></i>12. 弱点克服！MDwikiをGoogle検索の対象にする