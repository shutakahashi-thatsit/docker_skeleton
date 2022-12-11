# docker立ち上げたらすぐにlaravel使える状態になってます

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

- 以下にアクセスしたらlaravelのTOPページが表示される(はず)

http://localhost:8000/