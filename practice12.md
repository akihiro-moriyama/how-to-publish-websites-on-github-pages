# 実践12. 弱点克服！MDwikiをGoogle検索の対象にする

## MDwikiで作ったサイトを検索で見つけられない理由

MDwikiで作ったサイトは基本的には検索で見つけることができません。これにはいくつかの理由があります。

### 理由1：サイト運営者がGoogleにサイトを登録していない

Googleやbingなどの検索サービスは、ロボットと呼ばれる自動プログラムによって常にインターネット上に新しいウェブサイトがないかを探していますが、ウェブサイト数の爆発的に増えた現代においては、偶然ロボットに発見してもらえることを期待することは宝くじの当選を期待するようなものです。サイト運営者がGoogleやbingにサイトを登録する必要があります。

### 理由2：sitemap.xmlがない

sitemap.xmlは、Googleやbingなどの検索サービスにウェブサイトのページ構成を知らせるための「URLの一覧表」です。MDwikiはsitemap.xmlを自動生成しないため、MDwikiで構築されたウェブサイトでGoogle検索の対象となるのは index.html (mdwiki.htmlをリネームしたもの) だけになります。

### 理由3：Googleにおける「#!」を含むURLの扱い
ウェブページのURLが文字列`#!`を含む場合、GoogleはURLの当該箇所を`?_escaped_fragment_=`に置き換えてからそのウェブページが実在するかどうかを確認しに行きます。MDwikiはGoogleのこの仕様に対応していないので、Googleはページは実在しないと判断し、Google検索から除外します。よってたとえsitemap.xmlがあったとしても、MDwikiで構築されたウェブサイトでGoogle検索の対象となるのは index.html (mdwiki.htmlをリネームしたもの) だけになります。




## sitemap.txtを作成する

検索サービス向けのサイトマップは、一般的にはsitemap.xmlというファイル名のXML構文で書かれたテキストで表現するのが一般的ですが、実はXML構文を一切用いないURLの羅列であっても問題ありません。その場合はsitemap.txtというファイル名になります。

ここでのポイントは、MDwikiのコンテンツデータである.mdファイルのURLをそのまま書いている点です。.mdファイルをウェブブラウザで (MDwikiを介さずに) 表示すると文字化けするので本来はお勧めできませんが、検索されないよりはマシです。

### sitemap.txtの例

```
http://www.example.com/
http://www.example.com/index.html
http://www.example.com/content01.md
http://www.example.com/content02.md
　：
http://www.example.com/content99.md
```

### NG

```
http://www.example.com/index.html#!content01.md
```

### Okey

```
http://www.example.com/content01.md
```




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