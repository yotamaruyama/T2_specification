pip list
devcontainer.jsonをかいて
docker fileを書いたからうまく行ったみたい

root@67bb2f216231:/workspaces/dango_sample_app# django-admin  startproject djangopj .

Nginxの設定とDockerfile自体は基本的には問題ないように見えますが、いくつかの点を確認してみましょう。

コンテナ間の名前解決: docker-compose.ymlでDjango（Gunicorn）を動かすサービスの名前がappである必要があります。Nginxの設定（default.conf）でupstream djangoセクションでserver app:8000;とありますので、このappはDjango（Gunicorn）のサービス名と一致していなければなりません。

静的ファイル: location /static/でalias /static/;とありますが、この/static/はコンテナ内でDjangoが静的ファイルを保存する場所と一致している必要があります。Djangoのsettings.pyでSTATIC_ROOTがどう設定されているかによります。

docker-compose.ymlの更新: Nginxのサービスをdocker-compose.ymlに追加する必要があります。

例:

yml
Copy code
version: '3'
services:
  web: # この名前がappと同じであれば問題ありません。そうでなければ、Nginxの設定を更新する必要があります。
    build: ./web
    ...
  nginx:
    build: ./containers/nginx
    ports:
      - "80:80"
    depends_on:
      - web # Nginxがwebサービス（Django/Gunicorn）に依存していることを明示
  ...
パスとボリューム: Dockerfileや設定ファイルがある場所を正確に指定する必要があります。例えば、COPY containers/nginx/conf.d/default.conf /etc/nginx/conf.d/default.confのcontainers/nginx/conf.d/default.confはDockerfileがある場所からの相対パスまたは絶対パスでなければなりません。
これらの点を確認・調整した後、全体の設定が適切であれば問題なく動作するはずです。