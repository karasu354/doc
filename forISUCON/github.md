# github

[手順書一覧に戻る](./README.md)

## `git`のインストール
```
$ sudo apt-get install git
$ git --version
git version 2.25.1
```
## 初期の設定の確認
```
$ git config --list
(初期は何も設定しないから出ない)
```

## 最初の設定 (未完成)
次のようなシェルスクリプトを作り実行する
```
#!/bin/bash
git config --global user.name  "userName"
git config --global user.email "username@example.com"
```

## 管理したいフォルダでの設定
```
$ git init
$ git add .
$ git commit -m "init"
```

## GitHubのリポジトリで管理する方法(Deploy Key)
SSH-keyの生成
```
$ ssh-keygen
$ ls -al ~/.ssh
$ ssh-add -l
```
リポジトリ内でSetting->Deploy keys->Add deploy keyで上で生成した公開鍵を登録する

公開鍵は以下のコマンドで確認する
```
$ cat ~/.ssh/id_rsa.pub
ssh-rsa .....=user@user
```
鍵を登録するさいにAllow write accessの項目があるが`push`を使用するならチェックを入れる

以下のコマンドで接続を確認する
```
$ ssh -T git@github.com
Hi hoge/hoge! You've successfully authenticated, but GitHub does not provide shell access.
```
成功すると上のように表示される
## GitHubのリポジトリを登録
SSHの方で登録
```
$ git remote add origin git@github.com:hoge/hoge.git
```
HTTPSの方で間違えて登録した場合は以下の方法で変える
```
$ git remote set-url origin git@github.com:hoge/hoge.git
```
## GitHubへPushする
```
$ git push origin master
```

## GitHubからPullする
```
$ git pull origin master
```