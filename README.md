# これをやるリポジトリ

https://docs.docker.jp/compose/django.html
※ ただし async にしたいのでちょこちょこ改造

## 対応する箇所

上記のドキュメントだけだと不完全なので、補完する情報を書く。
（これは docker compose コマンド（docker-compose コマンドではなく docker のサブコマンド）で実行しました）

docker compose run の前に docker compose build を行う。
それをしないと、ModuleNotFoundError: No module named 'django.utils.six.moves' エラーが出る

docker compose run コマンド自体も、 django-admin で動いた。
docker compose run web django-admin startproject atsu_pj .
ちなみに任意の名前でハイフンは使えない。 CommandError: 'a-tsu-pj' is not a valid project name. Please make sure the name is a valid identifier. のようなエラーが出る
