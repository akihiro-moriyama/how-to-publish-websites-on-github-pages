# 実践10. MDwikiをカスタマイズする・HTML編


## MDwikiをCSSファイルに対応させる

### CSSとは

CSSとは「カスケーディングスタイルシート」の略で、ウェブページ上の各パーツの見栄えに関する設定を一覧として一箇所にまとめたものです。昔はウェブページの各パーツごとに見栄えに関する設定を書き込んでいましたが、現在ではCSSファイルとしてひとまとめにするのが一般的です。

CSSはプログラム言語に似た専用の言語で記述するという決まりがあり、これをスタイルシート言語またはCSS言語と呼びます。

MDwikiは、MDwikiの本体であるindex.html (mdwiki.htmlをリネームしたもの)の中に直接CSS設定を書き込んでいますが、index.htmlの一部を書き換えることで、外部のCSSファイルをCSS設定として読み込むようになります。

### index.htmlを書き換える

#### 手順

1. プログラム開発用のunicode (UTF-8)対応テキストエディタを用意する。Windows付属の「メモ帳」アプリはUTF-8非対応なので使えない(2018年秋のアップグレードで対応の予定)

1. index.htmlをテキストエディタで開く

1. テキストエディタの文字列検索機能で`</head>`と書かれた箇所を探す

1. `</head>`と書かれた箇所のすぐ上に１行追加し、以下のように記述する

   ###### コード

   ```
   <link rel="stylesheet" href="style.css">
   ```

1. 文字コードの設定が＜UTF-8＞のままであることを確認し、上書き保存する

## MDwikiをFontAwesomeに対応させる

### FontAwesomeとは

FontAwesomeとは、スマートフォンアプリ等でよく使われるアイコンを文字として表現する、無料のウェブフォントです。

###### アイコンの例

* <i class="far fa-file fa-fw"></i>ファイル
* <i class="far fa-folder-open fa-fw"></i>フォルダ
* <i class="fas fa-cog fa-fw"></i>設定
* <i class="fas fa-paper-plane fa-fw"></i>送信
* <i class="fas fa-dog fa-fw"></i>イヌ
* <i class="fas fa-cat fa-fw"></i>ネコ

通常のフォントは、ウェブサイトの側でフォントを指定していたとしても閲覧者側のPCにフォントがインストールされていなければ文字化けを起こします。ウェブフォントであれば、ウェブサイト側でフォントを指定するだけで、文字化けすることなく誰でもウェブサイトを閲覧できます。

なお、FontAwesomeには無料版とPro版(有料版)の２つがありますが、ここでは無料版を使うものとします。

### ウェブページの本文でFontAwesomeを使う方法

FontAwesomeのアイコンはWindowsやMacのかな漢字変換では変換できません。まずFontAwesome公式ウェブサイトにあるアイコン一覧表より使いたい記号を探し、そのアイコンを表示するためのHTMLコードを書き写す必要があります。

なお、マークダウン記法で書かれるウェブコンテンツでその一部だけをHTMLコードで記述した場合、正しくHTMLとして認識されますのでご安心ください。

#### 基本的な使い方

1. FontAwesome公式ウェブサイトを開く https://fontawesome.com/icons
1. 一覧表の中から使いたいアイコンを探し、クリックしてアイコン詳細ページを開く
1. アイコン詳細ページ上方の`<i class="** fa-**"></i>`と書かれた箇所をクリックし、クリップボードに文字列をコピーする
1. マークダウン記法で書かれているコンテンツに上記のHTMLコードを貼り付ける

#### 備考

* 例えばネコのアイコンを使いたい場合は`<i class="fas fa-cat"></i>`というHTMLコードを使う

* 例えばネコのアイコンの詳細ページは https://fontawesome.com/icons/cat?style=solid である

* 使いたいアイコンを探す際は、FontAwesome公式サイトの画面上方にあるキーワード検索、または画面左の絞込検索を使うと探しやすい

* アイコンのサイズは最大5倍まで拡大表示できる。例えば5倍サイズで表示したい場合は`fa-5x`という文字列を追記する

  ```
  <i class="fas fa-cat fa-5x"></i>
  <i class="fas fa-cat fa-4x"></i>
  <i class="fas fa-cat fa-3x"></i>
  <i class="fas fa-cat fa-2x"></i>
  <i class="fas fa-cat"></i>
  ```

  > <i class="fas fa-cat fa-5x"></i><i class="fas fa-cat fa-4x"></i><i class="fas fa-cat fa-3x"></i><i class="fas fa-cat fa-2x"></i><i class="fas fa-cat fa-1x"></i>

### index.htmlを書き換える

MDwikiは、初期状態ではFontAwesomeに対応していませんが、index.html (mdwiki.htmlをリネームしたもの)の一部を書き換えることでFontAwesomeを使用できるようになります。

#### 手順

1. プログラム開発用のunicode (UTF-8)対応テキストエディタを用意する。Windows付属の「メモ帳」アプリはUTF-8非対応なので使えない(2018年秋のアップグレードで対応の予定)

1. index.htmlをテキストエディタで開く

1. テキストエディタの文字列検索機能で`</head>`と書かれた箇所を探す

1. `</head>`と書かれた箇所のすぐ上に１行追加し、以下のように記述する

   ###### コード

   ```
   <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.3/css/all.css">
   ```

1. 文字コードの設定が＜UTF-8＞のままであることを確認し、上書き保存する

## MDwikiをOGPに対応させる

### OGP (Open Graph Protocol)とは

ウェブページがFacebookやTwitterでシェアされた際、そのページのタイトルやサムネイル画像を表示させる仕組みのことです。

ウェブページをシェアしたいユーザーは、ただURLリンクを投稿するだけでよく、タイトルやサムネイル画像はFacebookやTwitterのシステムが自動的にウェブページより入手します。

### index.htmlを書き換える

MDwikiは、OGPに対応していませんが、index.html (mdwiki.htmlをリネームしたもの)に直接OGPに関する記述を追加することで、OGPを使用できるようになります。

ただし、その場合のOGP設定はMDwikiで作られたウェブサイト内の全ページ共通の設定として使用されます。MDwikiでは、個々のページにOGPを設定することはできません。

#### 手順

1. プログラム開発用のunicode (UTF-8)対応テキストエディタを用意する。Windows付属の「メモ帳」アプリはUTF-8非対応なので使えない(2018年秋のアップグレードで対応の予定)

1. index.htmlをテキストエディタで開く

1. テキストエディタの文字列検索機能で`</head>`と書かれた箇所を探す

1. `</head>`と書かれた箇所のすぐ上に、以下を追加記述する

   ###### コード

   ```html
   <!-- OGP -->
   <!-- author 作者名 -->
   <meta name="author" content="●●●●">
   <!-- keywords キーワード -->
   <meta name="keywords" content="●●●●">
   <!-- description ウェブサイトの概要説明 -->
   <meta name="description" content="●●●● ●●●● ●●●● ●●●●" />
   <!-- og:locale ウェブサイトの地域(言語) -->
   <meta property="og:locale" content="ja_JP" />
   <!-- og:type ウェブサイトの種類(サイトorブログ) -->
   <meta property="og:type" content="website" />
   <!-- og:title ウェブページのタイトル(MDwikiの場合はウェブサイトのタイトル) -->
   <meta property="og:title" content="●●●●" />
   <!-- og:description ウェブサイトの概要説明(もう一度書く) -->
   <meta property="og:description" content="●●●● ●●●● ●●●●" />
   <!-- og:url ウェブサイトのURL -->
   <meta property="og:url" content="https:●●●● ●●●● ●●●● ●●●●" />
   <!-- og:site_name ウェブサイトのタイトル -->
   <meta property="og:site_name" content="●●●●" />
   <!-- og:image アイキャッチ画像 -->
   <meta property="og:image" content="https:●●●● ●●●● ●●●●/eyecatch.jpg" />
   <!-- og:image:width アイキャッチ画像の幅pixel -->
   <meta property="og:image:width"  content="●●●●" />
   <!-- og:image:height アイキャッチ画像の高さpixel -->
   <meta property="og:image:height" content="●●●" />
   <!-- twitter:card Twitterでカード表示される際の種類 -->
   <meta name="twitter:card" content="summary" />
   <!-- END OGP -->
   ```

1. 文字コードの設定が＜UTF-8＞のままであることを確認し、上書き保存する

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
* <i class="far fa-hand-point-right fa-fw"></i>10. MDwikiをカスタマイズする・HTML編
* [11. MDwikiをカスタマイズする・CSS編](practice11.md)
* [12. 弱点克服！MDwikiをGoogle検索の対象にする](practice12.md)