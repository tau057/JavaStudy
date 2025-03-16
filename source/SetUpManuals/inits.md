# 事前にインストールしておいてほしいもの

開発に必要なツールや、サイトへのユーザー登録について記載。

## GitHubのユーザー登録

後述のGit操作や、その他サービスへの連動をWeb画面から行えるようになります。  
下記の公式サイトリンクから、SignUpしてください。

- [公式サイト](https://github.com/)

- 懸念POINT
  - 二段階認証の設定が必須だったような、そうじゃないような。何かトラブったら一緒に解決しましょう。
  - 仮に必要になったら、WinAuthあたりが使いやすくておすすめ。

## Git/TortoiseGitのインストール・日本語化

- Git(ギット)：バージョン管理ツール
- TortoiseGit(トータスギット)：Gitをグラフィカルに使いやすくするツール

下記リンクの手順を行うこと。（結構長いので、時間があるときに。）

- [Git for Windows と TortoiseGit のインストール【改訂版】](https://qiita.com/mmake/items/63a869272c0dfa1d50a4)

## VSCodeインストール

いわゆる統合開発環境です。  
研修で使用したであろう、Eclipceのようなもの。  

- [公式サイトのDLリンク](https://code.visualstudio.com/download)
  - Windowsのx64でいいと思う。（皆PC、Macじゃないよね？）

## JDKのインストール、パスの設定

javaを使用できるようにするための設定です。
下記のQiitaの記事を参考に、JDKのインストール＋パスの設定をします。

- [Windows PCにJDKのインストール & 環境変数の設定 & PATHを通すまで](https://qiita.com/Keichan_15/items/2a32f592ffeacd10e3f3)
  - [Oracle公式のJDKのDLページ](https://www.oracle.com/java/technologies/downloads/)

これも長いけど、最後の
```
javac --version
```
の結果が出るようになればOKだと思う。
