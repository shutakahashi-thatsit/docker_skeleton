# TOP表示までの手順
## laravel の各種設定

- .envファイルの作成

laravel ディレクトリ配下にある、「.env.example」をコピペ、コピペしたファイルの名前を「.env」に変更。

- laravel ディレクトリに移動
`$cd laravel`

- composer アップデート(インストール)
`composer update`

- Laravelプロジェクトに暗号化キーを設定
`php artisan key:generate`

## docker 立ち上げ

- 初期動作、コンテナを作る。結構時間がかかるけど終わるまで待つ。

`$ docker-compose build`

- コンテナ起動。完了後DockerDesktopを見に行ったらコンテナが立ち上がってる。

`$ docker-compose up -d`

- コンテナ終了(削除ではなく電源OFF)

`$ docker-compose stop`

### おまけ
- docker の laravel_app コンテナに侵入する方法。ssh 的なノリ。

`$ docker exec -it laravel_app bash`

- 以下にアクセスしたらlaravelのTOPページが表示される(はず)

http://localhost:8000/