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

viteコマンドを使ってプロジェクトを作成
yarn devで起動確認

### CLIを使ったStatic Web Appsのエミュレーション

CLIでyarn devの挙動を確認

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
