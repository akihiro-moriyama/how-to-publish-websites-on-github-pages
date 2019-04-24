# MDwiki 解説

## MDwikiとは
MDwikiは、JavaScriptで開発されたシンプルで軽量なCMS(コンテンツ・マネジメント・システム)です。

MDwikiの最大の特徴は、CMSを構成するファイルがHTMLファイルひとつしかないということです。非常にシンプルでコンパクトなCMSではありますが、その代わり多機能ではありません。マークダウン記法で書かれたウェブコンテンツをHTMLに変換する以外は他に目立った機能がほとんどないという変わり種のCMSです。

hint: MDwikiはJavaScriptで開発されたCMSであるためGitHub Pages上で運用可能です。

## MDwikiの最小構成

最低限2つのファイルをウェブサーバー上に置けばMDwikiは動作します。サーバーアプリケーションにありがちなコマンドラインを用いたインストールは必要ありません。

### 例

#### 1. ウェブサーバー内のファイルの配置

```
(http://www.example.com/)
├ index.html
└ index.md
```

#### 2. ウェブブラウザのURL欄への入力

```
http://www.example.com/
```

#### 3. MDwikiによって転送される先のURL

```
http://www.example.com/#!index.md
```

## MDwikiの使い方

使い方の詳細は、当サイトの「[実践編04 MDwikiを入手する](practice04.md)」およびそれ以降の章をご覧ください。