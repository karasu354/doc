# Access Log Profiler

[手順書一覧に戻る](./README.md)

## alpとは
alpはアクセスログ解析ツール

## alpインストール

```bash
wget https://github.com/tkuchiki/alp/releases/download/v1.0.9/alp_linux_amd64.zip && \
unzip ./alp_linux_amd64.zip && \
sudo mv ./alp /usr/local/bin/
```

別のインストール方法

```bash
wget https://github.com/tkuchiki/alp/releases/download/v1.0.9/alp_linux_amd64.zip && \
unzip alp_linux_amd64.zip && \
sudo install ./alp /usr/local/bin/alp
```

ちゃんとインストールされてるかの確認

```bash
alp --help
```

## nginx側の設定

nginxの設定ファイルを修正する

```bash
sudo nano /etc/nginx/nginx.conf
```

以下の部分に付け加える

```txt
http {
  ...
  log_format ltsv "time:$time_local"
                "\thost:$remote_addr"
                "\tforwardedfor:$http_x_forwarded_for"
                "\treq:$request"
                "\tstatus:$status"
                "\tmethod:$request_method"
                "\turi:$request_uri"
                "\tsize:$body_bytes_sent"
                "\treferer:$http_referer"
                "\tua:$http_user_agent"
                "\treqtime:$request_time"
                "\tcache:$upstream_http_x_cache"
                "\truntime:$upstream_http_x_runtime"
                "\tapptime:$upstream_response_time"
                "\tvhost:$host";

    access_log  /var/log/nginx/access.log ltsv;

  ...
}
```

(`access_log  /var/log/nginx/access.log ltsv;`を入れるかどうかわからない。いれたら実行したときにちゃんと出力される)

アクセスログファイルの削除と設定を反映するためにnginxをリロード

```bash
sudo rm /var/log/nginx/access.log && sudo systemctl reload nginx
```

## アクセスログの確認方法

```bash
alp ltsv --file=/var/log/nginx/access.log
```

もしくは

```bash
cat /var/log/nginx/access.log | alp ltsv
```

## アクセスログのオプション
```bash
cat /var/log/nginx/access.log | alp ltsv\
-m "image/[0-9]+"\
--sort=count -r
```

- `-m` URIをまとめる
- `-sort` [count|avg|etc...]でソートする
- `-r` 降順にソート

詳しくは、https://github.com/tkuchiki/alp
