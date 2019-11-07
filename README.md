### PlayCanvasのプロジェクトをデプロイをするサンプルをおいているプロジェクトになります。
使い方については、README.mdに加えて、[こちら](https://qiita.com/yushimatenjin/items/8a6637358a5f6b755cd2)のQiitaの記事があります。

基本的にこのプロジェクトをcloneしていただけると使えるようになっております。
`.github/workflows/*`に複数デプロイのためのスクリプトが入っております。

- `Firebase Hosting`にデプロイをする
  `.github/workflows/deploy-firebase.yml`

- `SSHでウェブサーバー`にデプロイをする
  `.github/workflows/deploy-ssh.yml`

現在この2つのデプロイ方法のサンプルがあります。


### 1. リポジトリをクローンする

```bash
git clone git@github.com:yushimatenjin/playcanvas-deploy-workflow.git
```



| 環境変数                | 値          | 取得先                          |
|-------------------------|-------------|---------------------------------|
| PLAYCANVAS_ACCESS_TOKEN | accessToken | playcanvas.json                 |
| PLAYCANVAS_BRANCH_ID    | branchId    | playcanvas.json                 |
| PLAYCANVAS_PROJECT_ID   | projectId   | playcanvas.json                 |
| PLAYCANVAS_PROJECT_NAME | projectName | playcanvas.json                 |
| PLAYCANVAS_REMOTE_PATH  | remotePath  | playcanvas.json                 |
| PLAYCANVAS_SCENES       | scenes      | playcanvas.json                 |
| FIREBASE_TOKEN          | token       | Firebase CLI                    |
| PROJECT_ID              | projectId   | Firebase CLI / Firebase管理画面 |

