# github

[一覧に戻る](./README.md)

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

## 最初の設定
次のようなシェルスクリプトを作り実行する
```
#!/bin/bash
git config --global user.name  "userName"
git config --global user.email "username@exmaple.com"
```