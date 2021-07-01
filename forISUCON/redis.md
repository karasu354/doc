# Title

[手順書一覧に戻る](./README.md)

## Redisのインストール
```
$ sudo apt update
$ sudo apt install redis-server
```
`supervised`ディレクティブを`systemd`に変更
```
$ sudo nano /etc/redis/redis.conf

---------- /etc/redis/redis.conf ----------
...
supervised systemd
...
```
Redisサービスを再起動
```
$ sudo systemctl restart redis.service
```

## Redisの起動確認
Redisサービスが起動しているかを確認
```
$ sudo systemctl status redis
```
Redisが正しく機能しているか
```
$ redis-cli
127.0.0.1:6379> ping
PONG
```