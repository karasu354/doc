# Webアプリのソース管理

## 前提条件

[Serverの初期設定](./server-init.md)
が完了していること

## git init

**ポイント**

https://www.toptal.com/developers/gitignore/api/go から gitignoreの雛形を取ってきている
これをベースにgit statusなどでいい感じにgitignoreを最速で仕上げる

```console
$ cd $HOME/webapp
$ git init
$ wget https://www.toptal.com/developers/gitignore/api/go -O .gitignore
$ git status
$ git add .
$ git commit -m "init"
$ git remote add origin git@github.com:isu-aroe/isu12-webapp.git
$ git branch -M  "main"
$ git push -u origin "main"
```