# Access Log Profiler

[手順書一覧に戻る](./README.md)

## alpインストール
```
$ wget https://github.com/tkuchiki/alp/releases/download/v0.3.1/alp_linux_amd64.zip
$ unzip alp_linux_amd64.zip
$ sudo mv alp /usr/local/bin/
```
別のインストール方法
```
$ wget https://github.com/tkuchiki/alp/releases/download/v0.3.1/alp_linux_amd64.zip
$ unzip alp_linux_amd64.zip
$ sudo install ./alp /usr/local/bin
```
ちゃんとインストールされてるかの確認
```
$ alp --help
```

## nginx側の設定
nginxの設定ファイルを修正する
```
$ sudo nano /etc/nginx/nginx.conf
```
以下の部分に付け加える
```
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
アクセスログファイルの削除と設定を反映するためにnginxをリロード
```
$ sudo rm /var/log/nginx/access.log && sudo systemctl reload nginx
```

## アクセスログの確認方法
```
$ alp -f /var/log/nginx/access.log
```
もしくは
```
$ cat /var/log/nginx/access.log | alp
```
