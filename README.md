# docker, laravel構築手順

laravel ブランチでは laravel8 がインストール済なので、laravel インストールの手順を踏まなくても docker 立ち上げだけですぐに使えます。

laravel のバージョンを変更したい場合などに、以下の手順の　laravel8　のバージョン指定を変えてください。

## docker 立ち上げ

- 初期動作、コンテナを作る。結構時間がかかるけど終わるまで待つ。

`$ docker-compose build`

- コンテナ起動。完了後DockerDesktopを見に行ったらコンテナが立ち上がってる。

`$ docker-compose up -d`]

- コンテナ終了(削除ではなく電源OFF)

`$ docker-compose stop`

### おまけ
- docker の laravel_app コンテナに侵入する方法。ssh 的なノリ。

`$ docker exec -it laravel_app bash`

## laravel インストール

- laravel8 インストール

`composer create-project laravel/laravel:^8.* laravel`

- 以下にアクセスしたらlaravelのTOPページが表示される(はず)

http://localhost:8000/

### log 権限でこけたら以下も実行してください。

- log ディレクトリ権限変更

`chmod 777 laravel/storage/logs/`

- storage ディレクトリ権限変更

`xxx:/var/www/html $ chmod -R guo+w laravel/storage`

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