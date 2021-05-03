# 実践11. MDwikiをカスタマイズする・CSS編

## CSSとは

CSSとは「カスケーディングスタイルシート」の略で、ウェブページ上の各パーツの見栄えに関する設定を一覧として一箇所にまとめたものです。昔はウェブページの各パーツごとに見栄えに関する設定を書き込んでいましたが、現在ではCSSファイルとしてひとまとめにするのが一般的です。

CSSはプログラム言語に似た専用の言語で記述するという決まりがあり、これをスタイルシート言語またはCSS言語と呼びます。

## CSSカスタマイズの基本的な手順

MDwikiのCSSカスタマイズは、以下の手順で行います。

#### 手順

1. 未記入のstyle.cssを用意する(詳細後述)
1. MDwikiをstyle.cssに対応させる(詳細後述)
1. ウェブブラウザでカスタマイズしたいウェブページを開き、見栄えを変更したい部分を文字列選択する
1. 該当するCSS設定を表示する(詳細後述)
1. 該当するCSS設定をコピーする
1. style.cssをテキストエディタで開き、前述5の内容をペーストする
1. 値の部分を書き換える
1. style.cssを上書保存する

## 未記入のstyle.cssを用意する

新しいCSS設定を書き込む場所としての未記入のstyle.cssを用意します。

CSSファイルは、基本的には拡張子を「.txt」から「.css」に書き換えただけのテキストファイルです。CSSファイルのファイル名は『style.css』とするのが一般的です。

CSSファイルをテキストエディタで作成する際は文字コードを＜UTF-8＞に設定します。

#### 手順

1. プログラム開発用のunicode (UTF-8)対応テキストエディタを用意する。Windows付属の「メモ帳」アプリはUTF-8非対応なので使えない(2018年秋のアップグレードで対応の予定)

1. テキストファイルを新規作成する

1. 文字コードの設定を＜UTF-8＞とする

1. 1行目に、以下のように記述する。2行目以降は今は何も書かない

   ```
   @charset “UTF-8”;
   ```

1. [名前をつけて保存]を実行し、ファイル名を『style.css』とする

1. style.cssファイルをindex.html(mdwiki.htmlをリネームしたもの)と同じフォルダに配置する

   ###### 配置例
   
   ```
   (作業ディレクトリ)
   　├ index.html
   　├ style.css
   　：
   　：
   　├ example98.md
   　└ example99.md
   ```

## MDwikiをsyle.cssに対応させる

MDwikiでは、MDwikiの本体であるindex.html (mdwiki.htmlをリネームしたもの)の中に直接CSS設定を書き込んでいますが、index.htmlの一部を書き換えることで、外部のCSSファイルをCSS設定として読み込むようになります。

#### 手順

1. プログラム開発用のunicode (UTF-8)対応テキストエディタを用意する。Windows付属の「メモ帳」アプリはUTF-8非対応なので使えない(2018年秋のアップグレードで対応の予定)

1. index.htmlをテキストエディタで開く

1. テキストエディタの文字列検索機能で`</head>`と書かれた箇所を探す

1. `</head>`と書かれた箇所のすぐ上に１行追加し、以下のように記述する

   ###### コード

   ```
   <link rel="stylesheet" href="style.css">
   ```

1. 文字コードの設定が＜UTF-8＞のままであることを確認し、index.htmlを上書き保存する

## ローカルにあるMDwiki(index.html)をブラウザで表示する

ウェブブラウザは、インターネット上にあるHTMLファイルだけでなく、PCに接続されたローカルなドライブ内にあるHTMLファイルも表示できます。しかしながら近年のウェブブラウザは、悪意あるハッキングからユーザーを守るため、ローカルにあるHTMLファイルに記述されたJavaScriptを無視します。

つまりJavaScriptで動くウィキシステムであるMDwikiは、いったんインターネット上にアップロードしないと正常動作しないことになります。

ウェブブラウザのひとつFireFoxは、比較的簡単に、このJavaScriptを無視する機能を解除できます。以下に手順をご紹介します。**ただしセキュリティ面では弱体化することに注意してください**。

#### 手順

1. FireFoxを起動する
2. アドレスバーに`about:config`と入力して、キーボードの[Enter]キーを押す
   →警告メッセージが表示される
3. [危険性を承知の上で使用する]ボタンをクリックする
   →[高度な設定]タブが開く
4. [設定名を検索]欄に、`security.fileuri.strict_origin_policy`と入力する
   →隠れていた設定入力欄が現れる
5. [切り替え]ボタンをクリックして、設定を`true`から`false`へ変更する。
6. [高度な設定]タブを閉じる

## ブラウザでウェブページのCSS設定を表示する

CSSカスタマイズは、古い設定を新しい設定で上書きする形で行います。したがって、まず現状のCSS設定を知る必要があります。ほとんどのウェブブラウザには、現在表示しているウェブページのCSS設定を表示する機能があります。

#### Chromeの場合

ウェブページの見栄えを変更したい部分を文字列選択し、右クリックメニューより[検証]を選択する

#### Edgeの場合

ウェブページを表示した状態で、F12キーを押す

#### Safari(MacOS) の場合

まず環境設定画面で設定項目＜メニューバーに開発メニューを表示＞にチェックの入っていることを確認し、ウェブページを表示した状態で、メニューより[開発＞ウェブインスペクタを表示する]を選択する

#### FireFox の場合

ウェブページの見栄えを変更したい部分を文字列選択し、右クリックメニューより[要素を調査]を選択する

## 事例：コードブロックの行頭に行番号をつける

コードブロック`<pre><code>…</code></pre>`の行頭に擬似的に行番号をつけるCSS手法については、SaKuRaiさん https://www.studiomic.net/pre-line-numbers/ の解説を参考にしました。

#### 考え方

1. `<code>`のbefore擬似要素として`content`を挿入する
2. `content`の表示位置は`<pre>`に対する絶対座標で指定する。これにより`content`は`<code>`と重なるように表示される。
3. `content`は極端に縦に細長いブロック要素であるとする。結果として`content`は`<pre>`からはみ出す
4. `<pre>`に overflow-y属性=hidden と設定し、`<pre>`からはみ出した`content`を隠す。
5. `<pre>`に overflow-x属性=scroll と設定し、ソースコード文字列の1行が長すぎる場合はスクロールで表示するものとする
6. `content`に、1(改行)2(改行)3(改行)…と行番号を書く(とりあえず50まで書けば実用上の問題はないように思う)
7. `<pre>`,`<content>`,`<code>`の各寸法値を微調整することで、コードブロックに行番号が表示されているかのように表示される。

#### サンプル

```
pre *{font-size:14px;line-height:1.8;}
pre{padding:0;}
pre>code{padding-left:32px; margin:10px 10px 5px 10px;}
pre{position:relative}
pre>code:before{position:absolute; top:0px; left:0px;}
pre>code:before{width:32px; display:block; text-align:right; padding-top:10px; border-right:1px solid #ddd; color:#aaa; content:"1\A 2\A 3\A 4\A 5\A 6\A 7\A 8\A 9\A 10\A 11\A 12\A 13\A 14\A 15\A 16\A 17\A 18\A 19\A 20\A 21\A 22\A 23\A 24\A 25\A 26\A 27\A 28\A 29\A 30\A 31\A 32\A 33\A 34\A 35\A 36\A 37\A 38\A 39\A 40\A 41\A 42\A 43\A 44\A 45\A 46\A 47\A 48\A 49\A 50\A";}
pre{overflow-y:hidden;overflow-x:scroll;}
pre>code{white-space:pre;}


```



## 具体的なCSSのカスタマイズの具体例

当サイトもCSSをカスタマイズしています。以下URLより、本サイトで使用しているstyle.cssをウェブブラウザで表示できます。CSSカスタマイズの参考にしてください。

note: URL https://akihiro-moriyama.github.io/how-to-publish-websites-on-github-pages/style.css

## 関連ページ

----

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
* <i class="far fa-hand-point-right"></i>11. MDwikiをカスタマイズする・CSS編
* [12. 弱点克服！MDwikiをGoogle検索の対象にする](practice12.md)