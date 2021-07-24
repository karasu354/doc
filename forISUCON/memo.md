# Title

[手順書一覧に戻る](./README.md)

## まとめてないものをまとめるやつ
```
sudo usermod -aG docker user_name
```
```
docker exec -it <id> bash
```

- `Apparmor`の無効化について
`my.cnf`にシンボリックリンクで管理しても動かん！解決方法↓
```
sudo ln -s /etc/apparmor.d/usr.sbin.mysqld /etc/apparmor.d/disable/
sudo apparmor_parser -R /etc/apparmor.d/disable/usr.sbin.mysqld
```