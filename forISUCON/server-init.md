# サーバ初期設定

[手順書一覧に戻る](./README.md)

## ServerからGitHubにpushする準備

```console
$ ssh <isucon server>
$ sudo su - isucon
$ mkdir -p ${HOME}/.ssh && chmod 700 ${HOME}/.ssh
$ echo -e "Host github github.com\n    HostName github.com\n    IdentityFile ~/.ssh/github-push\n    User git" > ${HOME}/.ssh/config
$ ssh-keygen -t rsa -f ${HOME}/.ssh/github-push -P "" && cat ${HOME}/.ssh/github-push.pub
```

出力された公開鍵を以下の2箇所に追記する
- [etcファイル群用のGitHub RepoのDeploy設定](https://github.com/isu-aroe/isu12-etc/settings/keys/new)
- [アプリソース用のGitHub RepoのDeploy設定](https://github.com/isu-aroe/isu12-webapp/settings/keys/new)

GitHubへのDeploy Keyが正しく設定されたかを確認する
```console
ssh -T github
```
