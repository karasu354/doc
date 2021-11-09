# python
仮想環境
```sh
python -m venv .venv
```

formatter `black`
```sh
pip install black
```

linter `mypy`
```sh
pip install mypy
```

import sorter `isort`
```sh
pip install isort
```


| 設定名 | 機能 | コマンド |
| ---- | ---- | ---- |
| [editor] |||
| tabSize | 単語の区切り文字 ||
| formatOnSave | 保存するときにフォーマット ||
| formatOnPaste | 貼り付けた内容が自動的にフォーマット ||
| formatOnType | 入力後に自動的にフォーマット ||
| insertSpaces | コメント時に空白文字を挿入する ||
| [python] |||
| pythonPath | Pythonへのpath ||
| venvPath | 仮想環境へのpath ||
| [python.formatting] |||
| provider | Pythonコードの整形に何を使用するか ||
| blackPath | blackへのpath ||
| [python.linting] |||
| enabled | Lint機能を有効にするかどうか | |
| mypyEnabled | Linterにmypyを使用するかどうか | |
| mypyArgs | mypyの設定 | |
| [python.linting.mypyArgs] |||
| --ignore-missing-imports | 型の無いモジュールのインポートを無視 | |
| --follow-imports | 再帰的に型チェックしていくルール | |
| [--follow-imports=] silent | 全てのインポートで型チェックを行う．エラーメッセージが表示されない | |
| --show-column-numbers | エラー発生箇所を行列数で表示 | |
| --check-untyped-defs | アノテーションされていない関数でも，関数内の型アノテーションをチェック | |
| [python.sortImports] |||
| path | sortimportsへのpath ||

## 備考
[mypyのコマンドライン](https://qiita.com/keng000/items/8e55e3cfdba888fba290)