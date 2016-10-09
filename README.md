StackStorm(st2sdk) Docker Containers
====

[st2sdk](https://github.com/StackStorm/st2sdk)を利用して、pack開発を進めるための環境です。  
公式の`st2sdk`が問題なく動くためのコンテナ一式です。

# 使い方

本リポジトリをcloneし、 `docker-compose up -d` で環境を起動してください。

その後、以下のコマンドで`dev`コンテナに接続します。

```
docker-compose exec dev /bin/bash
```

その後は、[st2sdk](https://github.com/StackStorm/st2sdk)にある好きなコマンドを実行しながらpack開発を進めることができます。

# 主なディレクトリ

* `/tmp/st2` : 公式の[st2](https://github.com/StackStorm/st2)リポジトリをcloneしています。これを`ST2_REPO_PATH`環境変数に指定することで、`st2sdk`コマンドは問題なく動くようになります。
* `/tmp/packs` : 開発対象のpackを配置するディレクトリです。コンテナ外部と連結しているため、一旦手元で作って、テストのときのみコンテナで実行、ということができます。一部の`st2sdk`のコマンドは、その上で`/tmp`をカレントディレクトリにして実行しないとエラーになるものがあります。
