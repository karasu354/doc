# MySQL

[手順書一覧に戻る](./README.md)

## スロークエリログ出力設定
`my.cnf`内で以下のように設定
```
$ sudo nano /etc/mysql/my.cnf

[mysqld]
slow_query_log = 1
slow_query_log_file = /var/log/mysql/slow.log
long_query_time = 0
```

設定を反映させるためにMySQLを再起動
```
$ sudo systemctl restart mysql
```
あるいは
```
$ sudo service mysql restart
```

設定の確認
MySQLにログイン
```
$ sudo mysql

mysql> show variables like 'slow%';
```

もし，このとき，`slow_query_log` がOFFな場合は，以下の点を確認する．
- `slow_query_log_file` に指定したファイルにmysqlがアクセス不可（権限・ファイルの存在）であるかどうか

↑な場合は **自動的にOFFになる** ので，ハマりポイント

## ログ解析
`mysqldumpslow`コマンド
```
$ mysqldumpslow -s t slow.log > dump
```
`-s`オプション
- `at` Queryの平均実行時間
- `c`  Queryの出現回数
- `ar` Query内で取得/更新した合計レコード行数
- `t`  Queryの合計実行時間