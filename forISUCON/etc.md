# NginxとMysqlの設定をGit管理下に移す

[手順書一覧に戻る](./README.md)

/etc/{nginx,mysql} にあると変更が追いづらいのでisucon userのホームディレクトリに持ってきてgit管理したい

## 前提条件

[Serverの初期設定](./server-init.md)
が完了していること

## 作業

User: isucon と想定する
```console
$ mkdir $HOME/etc
$ sudo cp --recursive /etc/{nginx,mysql} $HOME/etc/
$ sudo chmod --recursive isucon:isucon $HOME/etc/

$ sudo systemctl stop nginx
$ sudo mv /etc/nginx /etc/nginx-old
$ sudo ln -s $HOME/etc/nginx /etc/nginx
$ ls -la /etc/nginx
$ sudo systemctl restart nginx && systemctl status nginx
 
$ sudo systemctl stop mysql
$ sudo mv /etc/mysql /etc/mysql-old
$ sudo ln -s $HOME/etc/mysql /etc/mysql
$ ls -la /etc/mysql
$ sudo systemctl restart mysql && systemctl status mysql

ここまでで一度bench回して正常性を確認するとよい

$ cd $HOME/etc
$ git init
$ git add .
$ git commit -m "init"
$ git remote add origin git@github.com:isu-aroe/isu12-etc.git
$ git branch -M  "main"
$ git push -u origin "main"
```
