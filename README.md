# hanonage_electron
半音上げプラグイン大会で作成したUTAU用半音上げプラグインのElectron版です。

## 始め方
Node.js と、コマンドラインで作業する知識が必要です。

git 等でソースコードをとってきます。

```
 $ git clone https://github.com/hunyosi/hanonage_electron.git
```

パッケージングに必要なモジュールをローカルにインストールします。

```
 > cd hanonage_electron
 hanonage_electron> npm install
```

プラグイン本体に必要なモジュールをローカルにインストールします。

```
 hanonage_electron> cd app
 hanonage_electron\app> npm install
```

プラグインのインストール用のZIPを作ります。

```
 hanonage_electron\app> cd ..
 hanonage_electron> npm run build
```

しばらくすると、現在のディレクトリに hanonage_electron.zip ができます。
そのZIPをUTAUのウィンドウにD&Dすれば、プラグインが使えます。

このプラグインをもとに新しいプラグインを作ったりする場合には、動作確認用に npm で Electron をグローバルにインストールします。

```
 > npm install electron -g
```

動作確認する場合は、作成中のappディレクトリ内で次のようにします。

```
 app> electron . <テスト用の書き換わっていい.ustファイル>
```

新たに作ったプラグインを公開する場合には、以下のファイルを書き換えてください。
+ install.txt -- UTF-8で書いてください。パッケージングの際に自動でShift_JISに変換します。
+ plugin.txt -- UTF-8で書いてください。パッケージングの際に自動でShift_JISに変換します。
+ README.md -- 適当に書いてください。こちらは主に開発者向けになると思います。ZIPには含まれません。
+ LICENSE -- できればソフトウェア用の有名なライセンスを選んで、その本文をここに移すのが良いでしょう。
+ fordist/readme.txt -- ZIPファイル内に含まれるファイルです。ここに書かれているものを参考に、プラグインのユーザー向けにわかりやすく書いてください。
