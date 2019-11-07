# このリポジトリについて

PlayCanvasのプロジェクトをデプロイをするサンプルをおいているプロジェクトになります。
使い方については、README.mdに加えて、[こちら](https://qiita.com/yushimatenjin/items/8a6637358a5f6b755cd2)のQiitaの記事があります。

`.github/workflows/*`に複数デプロイのためのスクリプトが入っております。

- `Firebase Hosting`にデプロイをする
  `.github/workflows/deploy-firebase.yml`

- `SSHでウェブサーバー`にデプロイをする
  `.github/workflows/deploy-ssh.yml`

現在この2つのデプロイ方法のサンプルがあります。

#### 参考
[Firebase Hosting](https://firebase.google.com/docs/hosting?hl=ja)

# 使い方

必要なソフトウェア
- `Node.js`
- `Git`
- `npm`

### 使い方 

1. リポジトリをダウンロード

```bash
git clone git@github.com:yushimatenjin/playcanvas-deploy-workflow.git
```

※自身の環境変数を使用してGitHub Actionsを使用いたしますので、このときにPushをするためのリポジトリを新規にGitHubで作成をしておきます。

2. playcanvas.jsonを下記コマンドで生成

この際に必要となるAPIキーについては[こちら](https://playcanvas.com/account)から発行できます。

1. APIキーを入力
2. 対象のプロジェクト名を入力

```bash
 npx playcanvas-tools init
```

※上記コマンドを入力すると、カレントディレクトリに`playcanvas.json`が生成されます。


3. GitHubから環境変数を設定して`Push`


![https://camo.qiitausercontent.com/54cbf4156ef9c50cb35d852363d34ff4fdef15b1/68747470733a2f2f71696974612d696d6167652d73746f72652e73332e61702d6e6f727468656173742d312e616d617a6f6e6177732e636f6d2f302f3235373034382f34636639313565312d383666352d363865332d386534302d3435393335316665613231382e706e67](https://camo.qiitausercontent.com/54cbf4156ef9c50cb35d852363d34ff4fdef15b1/68747470733a2f2f71696974612d696d6167652d73746f72652e73332e61702d6e6f727468656173742d312e616d617a6f6e6177732e636f6d2f302f3235373034382f34636639313565312d383666352d363865332d386534302d3435393335316665613231382e706e67)

`playcanvas.json`を参考に環境変数を設定します。


| 環境変数                | playcanvas.jsonのキー          | 取得先                          |
|-------------------------|-------------|---------------------------------|
| PLAYCANVAS_ACCESS_TOKEN | accessToken | playcanvas.json                 |
| PLAYCANVAS_BRANCH_ID    | branchId    | playcanvas.json                 |
| PLAYCANVAS_PROJECT_ID   | projectId   | playcanvas.json                 |
| PLAYCANVAS_PROJECT_NAME | projectName | playcanvas.json                 |
| PLAYCANVAS_REMOTE_PATH  | remotePath  | playcanvas.json                 |
| PLAYCANVAS_SCENES       | scenes      | playcanvas.json                 |
| FIREBASE_TOKEN          | token       | Firebase CLI                    |
| PROJECT_ID              | projectId   | Firebase CLI / Firebase管理画面 |


※APIを発行したアカウントがPersonal, Organization以外のプランですと、プロジェクトのダウンロードができませんので、CIを使用したダウンロードでエラーが出ます。


4. リポジトリにPushをする
- 環境変数の設定ができたら、自身のGitHubのリポジトリに`Push`をします。


