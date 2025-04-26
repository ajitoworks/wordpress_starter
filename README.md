## はじめに
このレポジトリは、Docker + WordPress + MySQL + PHPMyAdminの構成テンプレートです。

## 必要環境
* Docker Desktop

### テンプレートの使い方
以下のコマンドを入力します。

```
git clone https://github.com/ajitoworks/wordpress_starter.git
./wordpress_starter
docker-compose up -d
```

| 起動するもの  | URL |
| ------------- | ------------- |
| WordPress | `http://localhost:8080` |
| PHPMyAdmin  | `http://localhost:8081`  |

* 初回立ち上げ時はWordPressのセットアップ画面が表示されるので、従ってください。

### 初期データの追加
* `/docker/db/sql/`配下にDBのダンプファイルを配置すると、Dockerコンテナ初回起動時にデータが流し込みされます。<br />開発時に初期データを固定化したい場合はダンプファイルを生成して配置してください。

### WordPressに関する補足
* 各プロジェクト用のレポジトリを作ったら、`/src/`配下に生成されたファイルはコミットしてしまうのが良いです。
  * `/src/`配下はテンプレートでは監視対象外に指定しています。各プロジェクトで固定化したいファイルはコミットされるように`.gitignore`を編集してください。
* 基本的には、WordPressのテーマの編集が主になると思います。<br />`/src/wp-content/themes/`ディレクトリに新規テーマのディレクトリを作成し、これをGit Submoduleとして別レポジトリで管理するのが良いでしょう。Docker環境とWPテーマを分離できるためです。