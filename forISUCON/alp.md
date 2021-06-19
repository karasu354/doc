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
```
http {
  ...
  log_format ltsv "time:$time_local"
    "\thost:$remote_addr"
    "\tforwardedfor:$http_x_forwarded_for"
    "\treq:$request"
    "\tmethod:$request_method"
    "\turi:$request_uri"
    "\tstatus:$status"
    "\tsize:$body_bytes_sent"
    "\treferer:$http_referer"
    "\tua:$http_user_agent"
    "\treqtime:$request_time"
    "\truntime:$upstream_http_x_runtime"
    "\tapptime:$upstream_response_time"
    "\tcache:$upstream_http_x_cache"
    "\tvhost:$host";

  access_log  /var/log/nginx/access.log ltsv;
  ...
}
```