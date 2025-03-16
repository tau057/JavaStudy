# Sphinxの設定~Cloudflareでのデプロイ

## 前提

- Pythonインストール
  - 記載略（公式サイト参照）

pipコマンドを使用して作業を進めるために必要。

## 作業概要

- pipenvのインストール、初期設定
- sphinxのインストール、初期設定
- requirement.txtの設定
- その他設定（デザイン）
  - mdファイルを使用可にする
  - sphinxのデザイン変更（thema/css）
- ローカル上でのdocument確認
- Cloudflareでのデプロイ

## 作業詳細

以降の作業は、指定がない場合sphinxプロジェクトのルートディレクトリで行う。

### pipenvのインストール、初期設定

以下のコマンドを実行する。

```
pip instal pipenv
pipenv --python 3.XX
```

XXの箇所は自身がインストールしたPythonのバージョンを指定する。  
上記操作で、pipfile、pipfile.lockが作成される。


```{note}
pipenvを使用して上記ファイルを作成することで、  
複数環境でバージョンなどを統一することが可能となる。
```

（参考）[Pipenvを使ったPython開発まとめ](https://qiita.com/y-tsutsu/items/54c10e0b2c6b565c887a)


### sphinxのインストール、初期設定

以下のコマンドを実行する。

```
pipenv install sphinx
sphinx-quickstart
```

sphinx-quickstartの際にいくつか対話型のコマンドが出る。  
build結果とsourceを分離する設定はyesとする。

（参考）[Sphinxの使い方．docstringを読み込んで仕様書を生成](https://qiita.com/futakuchi0117/items/4d3997c1ca1323259844)

### requirement.txtの設定

cloudflareでのデプロイ時に必要となるファイル。  
必要なライブラリを記載し、プロジェクトのルートディレクトリに配置する。

```
(記載例)
sphinx
myst_parser
sphinx_rtd_theme
```

### その他設定

#### mdファイルを使用可にする

以下のコマンドを実行する。

```
pipenv install myst_parser
```

conf.pyのectensionsにmyst_parserを追加する。

```
extensions = ["myst_parser"]
```

(参考)[markdown で sphinx する](https://qiita.com/ousttrue/items/82650a13a3d488806984)


#### sphinxのデザイン変更（thema/css）

以下のコマンドを実行する。

```
pipenv install sphinx_rtd_theme
```

source/conf.py以下のように修正する。

```
html_theme = 'sphinx_rtd_theme'
```

### ローカル上でのdocument確認

以下のコマンドを実行する

```
make html
```

このコマンドはmake.bat（バッチファイル）を、htmlという引数を付けて実行している。
用は、html形式のドキュメントに変換してビルド（見られる状態に）してね～っていう命令。
ということは、別形式（例えばＰＤＦ）とかもある...らしいけどこっちはまだ使ったことない。

### Cloudflareでのデプロイ

下記のサイトを参考に、設定を行う。

[Cloudflare Pages上でSphinxサイトを自動デプロイする](https://helve-blog.com/posts/python/sphinx-cloudflare-page-deploy/)

    プロダクション ブランチ：main
    プリセット：なし
    ビルド コマンド：make html
    ビルド出力ディレクトリ：build/html
    環境変数と値：PYTHON_VERSION...3.13（使ってるPythonのバージョン）

プロジェクトのルートディレクトリで、以下のコマンドを実行することでPythonのバージョンが確認可能。

```
python --version
```


```{attention}
上記ページでは、requirement.txtが必要であるとの記載はなく、  
pipfileのみでデプロイ可能とのことだが、うまくいかなかった。  
他の環境との同期のためにpipfileは残すが、上記の点は留意すること。
```
