# MS Tech Camp #12 SignalRとStatic Web Appsでサーバレスチャット開発ライブデモ

## 概要

## 環境

- Windows 10 Home
- VSCode
- Azure Functions Core Tools v4
- yarn
- Node.js v14
- Vue.js 3

## 手順

### Azure SignalR Serviceリソースの作成

### ローカルプロジェクトの初期化

<!-- viteコマンドを使ってプロジェクトを作成 -->
<!-- yarn devで起動確認 -->

まずは任意のディレクトリでターミナルを開き、
次のコマンドを実行します。

```
yarn create vite serverless-chat-signalr --template vue-ts
```

`yarn create vite <app-name>`とすることで
Viteのプロジェクトが初期化されます。
オプションで`vue-ts`
というテンプレートを指定するとTypeScriptでVue3を使った
プロジェクトが選択されます。

そのあと以下のコマンドで

1. ディレクトリを移動
2. 依存パッケージのインストール
3. devサーバの起動

を行います。

```sh
cd serverless-chat-signalr

yarn

yarn dev
```

`localhost:3000`にアクセスして次のような画面が出れば成功です。
画面が見えたらいったんdevサーバを`Ctrl+C`で落としましょう。

### CLIを使ったStatic Web Appsのエミュレーション

<!-- CLIでyarn devの挙動を確認 -->

続いてStatic Web Apps CLI（以下SWA CLI）
によるエミュレーションを行います。

次のコマンドでSWA CLIをインストールしましょう。
自分はローカル環境が汚れるのが嫌なのでプロジェクトにインストールしていますが
グルーバルインストールをするのが一般的なようです。

```sh
yarn add -D @azure/static-web-apps-cli
```

そして先ほど立ち上げたdevサーバを今度は
SWA CLIでエミュレーションしながら立ち挙げてみます。

```sh
yarn swa start http://localhost:3000 --run "yarn dev"
```

ここのコマンドはサーバをSWAにデプロイしたかのようにエミュレーション
させるためのコマンドです。
devサーバを立ち上げた状態でエミュレーションしてもよいのですが、
今回はrunオプションによってサーバの立ち上げも同時にやっています。

コマンドを実行するとログが一気に流れてきますが、
`localhost://4280`にアクセスして先ほど同様の画面が表示されれば
成功です。
そしてまたdevサーバを落としましょう。

### Azure Functionsの作成とエミュレーション

`/api/hello`を作って通信を確認

### SignalR Service関連のAzure Functionsを作成

`/api/negotiate`と`/api/sendMessage`を作る
/apiにアクセスしてテスト

### SignalR クライアントの実装

`@microsoft/signalr`を用いてメッセージ受信

### Azure Static Web Appsにデプロイ

SWAへのデプロイ

## 参考資料

- [Azure Functions における SignalR サービスのバインド](https://docs.microsoft.com/ja-jp/azure/azure-functions/functions-bindings-signalr-service)
- [Azure SignalRサービスドキュメント](https://docs.microsoft.com/ja-jp/azure/azure-signalr/signalr-overview)
- [Vite](https://ja.vitejs.dev/)
- [Azure Static Web Apps CLI](https://github.com/Azure/static-web-apps-cli)
