# 実践12. 弱点克服！MDwikiをGoogle検索の対象にする

## MDwikiで作ったサイトを検索で見つけられない理由

いくつか理由があります。

### 理由1：sitemap.xmlがない

sitemap.xmlは、Googleやbingなどの検索サービスにウェブサイトのページ構成を知らせるための「URLの一覧表」です。MDwikiはsitemap.xmlを自動生成しないため、検索の対象になりません。

### 理由2：Googleは「#!」を含むURLを無視する
Googleは、ウェブページがURLの途中に`#!`を含む場合、URLの当該箇所を`?_escaped_fragment_=`に置き換えてからそのウェブページが実在するかどうかを確認しに行きます。MDwikiはGoogleのこの仕様に対応していないので、Googleはページが存在しないと認識し、Google検索から除外します。よってMDwikiで構築されたウェブサイトでGoogle検索の対象となるのはindex.html (mdwiki.htmlをリネームしたもの) だけです。




## sitemap.txtを作成する

まず重要なポイントとして、作成することは「ほぼ」無駄です。



この制約を前提とした上で、index.html(mdwiki.htmlをリネームしたもの)をGoogle検索の対象とするためにsitemapが必要である、ということになります。

さて、sitemapは一般的にsitemap.xmlというファイル名のXML構文で書かれたテキストで表現するのが一般的ですが、XML構文を一切用いないURLの羅列であっても問題ありません。


## Google Search Consoleにウェブサイトを登録する




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