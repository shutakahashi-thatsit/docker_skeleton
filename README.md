# 手順
## docker 立ち上げ
初期動作、コンテナを作る。結構時間がかかるけど終わるまで待つ。
$ docker-compose build

コンテナ起動。完了後DockerDesktopを見に行ったらコンテナが立ち上がってる。
$ docker-compose up -d

## laravel インストール

docker の app コンテナに侵入。ssh 的なノリ。
$ docker exec -it laravel_app bash

laravel インストール
xxx:/var/www/html $ composer create-project laravel/laravel:^8.* laravel

log ディレクトリ権限変更
xxx:/var/www/html $ chmod 777 /var/www/html/laravelapp/storage/logs/

storage ディレクトリ権限変更
xxx:/var/www/html $ chmod -R guo+w /var/www/html/laravelapp/storage

以下にアクセスしたらlaravelのTOPページが表示される(はず)
http://localhost:8000/

## Docker Compose とは

- Dockerイメージのビルドや各コンテナの起動・停止などをより簡単に行えるようにするツール
- docker-compose.ymlを使用する
- コマンドは docker-compose ...

### docker-compose.ymlとは
- Dockerイメージをビルドするための情報（使用するDockerfile、イメージ名など）
- コンテナ起動するための情報（ホストとの共有ディレクトリ設定やポートフォワードなどの起動オプションなど）
- 使用するDockerネットワーク
などを定義するファイル

## 構築手順参考記事
参考というかもはやもろパクリ
https://qiita.com/neneta0921/items/22f9864b6f6ff6d36004