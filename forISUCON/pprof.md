# pprofの導入と計測

[手順書一覧に戻る](./README.md)

## pprofの導入

pprofのimportとエントリポイントを以下のようにする

```go
import (
	_ "net/http/pprof"
)

func main() {
	go func() {
		log.Fatal(http.ListenAndServe(":6060", nil))
	}()

```

## pprofによる計測

ベンチなどアクセスをしている際に以下コマンドをアプリホストで実行
```console
go tool pprof -http="0.0.0.0:22222" http://localhost:6060/debug/pprof/profile
```
