translate-django-ja
=========

これはDjangoドキュメントの翻訳プロジェクトです。


ツールキット
------------

本プロジェクトでは、CAT（Computer Aided Translation）ツールOmega-T v3.5.1を使います。

Omega-Tは、Javaで書かれたアプリケーションで、
翻訳メモリ、自動翻訳、用語集の管理・利用ができます。

またMS WordやLibreOffice(OpenDocument)形式を処理できます。
V3.5では、POfile形式が処理できます。

Git/Svnを認識して利用できます。

http://omegat.org/

作業準備
---------

作業を開始する前に、Omega-Tでチーム設定を行います。
Omega-Tを起動し、「設定」－「チーム．．．」を選択して、あなたの名前をいれてください。
この名前は、コミットメッセージに自動的に使用されますので、今後残ることに注意してください。


作業の始め方
-----------

Omega-Tのファイルメニューから、「チームプロジェクトのダウンロード」を選択し、GithubのクローンURLと、ローカルディレクトリを指定します。
ローカルディレクトリは、MyDocuments/Github等を指定するといいでしょう。
ID、パスワードを聞かれますので、GithubのID/パスワードを入力します。
「暗号化しないで保存」オプションをチェックすることで、再度の入力をせずにすみます。
Omega-Tは、sshによるアクセスに十分に対応できないようなので、httpsによるURLを使いましょう。

MFAによる認証を行っている場合は、パスワードとして、トークンを入力します。
トークンの取得方法は、以下のヘルプを参照してください。

https://help.github.com/articles/creating-an-access-token-for-command-line-use

2回目以降は、ダウンロードしたフォルダを開くと、自動的にgithubから最新をPullしてきます。


翻訳の実施とコミット
--------------------

ダウンロードすると、原文一覧が表示されます。
担当する原文を選択して、作業をおこなってください。
翻訳結果の訳文の生成とレビューは、プロジェクトの終盤で行います。
チームプロジェクトとしては、翻訳メモリ（/omegat/project_save.tmx)が、作業結果となります。
Omega-Tは、翻訳メモリから自動的に訳文を生成します。

Omega-Tで保存を選択すると、翻訳メモリ(/omegat/project_save.tmx)を保存し、自動コミットします。

Omega-Tは、django-level1.tmx、 django-level2.tmx、django-omegat.tmxファイルを同時に生成します。
これらは、他のツールでの利用のために、自動生成されるものです。

ディレクトリの構造
-------------------

ディレクトリ構造は、Omega-Tの既定にあわせてあります。

- dictionary: 辞書

  辞書フォルダには、StarDict形式の辞書を格納することで、自動的に辞書引きされます。
  たとえば、英字郎を使うには、変換が必要です。
  以下のブログを参考にして、変換してください。
  http://codnote.blogspot.jp/2010/01/i-installed-stardict-and-eijiro.html

  また、フリーの辞書については、
  http://abloz.com/huzheng/stardict-dic/ja/
  から入手できます。

  ライセンス管理のため、本ディレクトリは、リポジトリにコミットしないでください。

- glossary: 用語集

- tm: 参考翻訳メモリ

- source: 原文,ベースのPO形式ファイル

- target: 訳文出力、翻訳反映したPO形式ファイル

- omegat: Omega-Tの内部ファイル


ファイル形式
--------------

原文は、PO形式で準備します。
Transifexから、for translationでダウンロードし、上書きしてください。

用語集
タブ区切りファイルになります。
english <tab>  Japanese <tab> note
が書かれます。

翻訳メモリ
XML形式のTMX形式を利用します。



Known Issues
---------------

複数名で並行作業した場合に、用語集や翻訳メモリのコンフリクトが発生した場合の方法
について、確立したしくみがありません。

用語集は、テキスト形式であるので、通常のDiffマージにより実施可能とおもわれます。
翻訳メモリは、XML形式であるため、ツールの能力に依存します。

ツールは、こちらに有ります。
TMXMergerやTMXCleanerが使えます
http://www.omegat.org/ja/resources.html


ライセンス
------------------

This project is workking project and will be never released.
These materials are licensed by same as django itself, 3-clauses BSD style.

