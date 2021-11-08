# python

| 設定名 | 機能 |
| ---- | ---- |
| python.venvPath | 仮想環境のpath |
| python.linting.mypyEnabled | Linterにmypyを使用するかどうか |
| python.linting.enabled | Lint機能を有効にするかどうか |
| python.linting.mypyArgs | mypyの設定 |
| [mypyArgs] --ignore-missing-imports | 型の無いモジュールのインポートを無視 |
| [mypyArgs] --follow-imports | 再帰的に型チェックしていくルール |
| [follow-imports] silent| 全てのインポートで型チェックを行う．エラーメッセージが表示されない |
| [mypyArgs] --show-column-numbers | エラー発生箇所を行列数で表示 |
| [mypyArgs] --check-untyped-defs | アノテーションされていない関数でも，関数内の型アノテーションをチェック |

## 備考
[mypyのコマンドラインについ](https://qiita.com/keng000/items/8e55e3cfdba888fba290)