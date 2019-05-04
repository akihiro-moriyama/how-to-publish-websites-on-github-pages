# 実践09. MDwikiをカスタマイズする・基本編

## ナビゲーションメニューを追加する

MDwikiにナビゲーションメニューを表示させるには、「navigation.md」という名称のファイルをindex.html (mdwiki.htmlをリネームしたもの)と同じフォルダ内に配置します。

Attention: MDwikiにはウェブページの追加に合わせて自動的にナビゲーションメニューに項目を追加する機能がありません。ウェブページを追加した際はメニュー項目も手作業で追加してください。

###### 例

```
(作業ディレクトリ)
　├ index.html
　├ navigation.md
　：
　：
　├ example98.md
　└ example99.md
```

### 1. navigation.mdを作成する

navigation.mdもマークダウン記法で記述しますが、記述には決まったルールがあります。

### A. シンプルなナビゲーションメニューの場合

* 1行目は見出しh1としてサイトタイトルを記述
* 2行目は空白行 (マークダウン記法のルール)
* 3行目以降の1行ごとに1メニュー項目をリンク付き文字列として記述

### 例

```
# サイトタイトル

[ホーム](index.md)
[記事](example01.md)
[このサイトについて](example99.md)
```



### B. ドロップダウン式のナビゲーションメニューの場合

* ドロップダウンの親項目は`( )`カッコの中を空欄にする
* 親項目に続けて順序無リスト形式でサブメニュー項目を記述する
* 区切り線を入れたい時は半角ハイフン記号3つ(`<hr>`を意味する)を記述する

### 例

```
# サイトタイトル

[ホーム](index.md)
[記事]()

* [記事1](example01.md)
* [記事2](example02.md)
* [記事3](example03.md)
---
* [記事4](example04.md)
* [記事5](example05.md)
* [記事6](example05.md)

[このサイトについて](example99.md)
```



## テーマを変更する

MDwikiには配色やフォントを変更する「テーマtheme」と呼ばれる機能があります。細かく変更することはできませんが、あらかじめ用意されたテーマから一つを選ぶことはできます。

テーマは「ギミックGimmick」と呼ばれる機能のひとつです。ギミックには他にも、動画を挿入するギミック、GoogleMapの地図を挿入するギミックなどがあります。[ギミックの詳細はMDwiki公式サイト(英語)をご参照ください](http://dynalon.github.io/mdwiki/#!gimmicks.md)。

### テーマセレクタをナビゲーションメニューに追加する場合

前述のnavigation.mdの最後の行に`[gimmick:themechooser](Choose theme)`を追加してください。

### 例

```
# サイトタイトル

[ホーム](index.md)
[記事](example01.md)
[このサイトについて](example99.md)
[gimmick:themechooser](Choose theme)
```

### 常に特定のテーマでウェブサイトを表示する場合

前述のテーマセレクタによってテーマを自由に選べるようになりましたが、常にお気に入りのテーマでウェブサイトを表示するように設定することもできます。

前述のnavigation.mdの最後の行に、themechooserではなく今度は `[gimmick:theme](****)`を追加してください。`(****)`の部分にはあなたの好きなテーマ名称を記述してください。

### 例

```
# サイトタイトル

[ホーム](index.md)
[記事](example01.md)
[このサイトについて](example99.md)
[gimmick:theme](cosmo)
```



## ブラウザウインドウ(タブ)にサイトタイトルを表示する

## フッターエリアに著作権表記を追加する

### config.json の修正

## ブラウザウインドウ(タブ)にファビコンを表示する

ウェブブラウザのウインドウ（タブ）をよく見ると、ウェブサイト名称の先頭に小さなアイコンが表示されています。これをファビコンと言います。ファビコンはウェブサイトの運営者が用意するものです。

### favicon.pngを用意する

MDwikiでは寸法32×32ピクセルの.png形式のファイルをファビコンファイルとして使用します。

本来は、１つのファイルの中に複数サイズの画像を格納した.ico形式のファビコンファイルが良いとされていますが、作るのが面倒なので、ここでは.png形式のファビコンを使用します。

ファビコンの絵柄に特にこだわりがない場合は、フリー画像素材を配布しているサイトから気に入ったものをダウンロードして使用すればいいでしょう。

note: フリー画像素材配布サイトの例  
icooon-mono http://icooon-mono.com/  
icons8.jp https://icons8.jp/  
iconfinder.com https://www.iconfinder.com/search/?q=favicon



favicon.pngファイルをindex.html(mdwiki.htmlをリネームしたもの)と同じフォルダに配置してください。

###### 例

```
(作業ディレクトリ)
　├ index.html
　├ favicon.png
　：
　：
　├ example98.md
　└ example99.md
```

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
* <i class="far fa-hand-point-right fa-fw"></i>09. MDwikiをカスタマイズする・基本編
* [10. MDwikiをカスタマイズする・HTML編](practice10.md)
* [11. MDwikiをカスタマイズする・CSS編](practice11.md)
* [12. 弱点克服！MDwikiをGoogle検索の対象にする](practice12.md)