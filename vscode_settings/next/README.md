# Next
プロジェクト作成
```sh
npx create-next-app
```

## .vscode/settings.json
`JavaScript`,`tsx`,`TypeScript`,`tsx`に対応
### editor
| 設定名 | 機能 | コマンド |
| ---- | ---- | ---- |
| tabSize | 単語の区切り文字 ||
| formatOnSave | 保存するときにフォーマット ||
| formatOnPaste | 貼り付けた内容が自動的にフォーマット ||
| formatOnType | 入力後に自動的にフォーマット ||
| insertSpaces | コメント時に空白文字を挿入する ||
| defaultFormatter | 他のすべてのフォーマッタ設定よりも優先される、既定のフォーマッタ選択 ||
| codeActionsOnSave | 保存時に実行されるコードアクションの種類 ||
| source.fixAll.eslint | ESLint拡張昨日の対象ファイルの有効 ||
| javascript.format.enable | 既定のJavaScriptフォーマッタを有効 ||
### eslint
| 設定名 | 機能 | コマンド |
| ---- | ---- | ---- |
| enable | ESLintを有効 ||
| format.enable | ESLintをフォーマッタとして有効 ||

## .vscode/extensions.json
### recommendations
|||
| ---- | ---- |
| dbaeumer.vscode-eslint | https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint |
| esbenp.prettier-vscode | https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode |

## {react_project}/.eslintrc.json
```sh
npm i -D eslint-config-prettier @next/eslint-plugin-next eslint-plugin-react
```
TypeScript
```sh
npm i -D typescript @types/node @types/react
```
### extends
拡張機能の追加
| 設定名 | 機能 | リンクなど |
| ---- | ---- | ---- |
| eslint:recommended | eslintの推奨項目 | https://eslint.org/docs/rules/ 日本語だと[ここ](https://www.tam-tam.co.jp/tipsnote/javascript/post11934.html)|
| prettier | prettier | https://github.com/prettier/eslint-config-prettier |
| "plugin:@next/next/recommended" | nextの推奨項目 ||
### plugins
機能の追加
| 設定名 | 機能 | リンクなど |
| ---- | ---- | ---- |
||||
### parserOptions
| 設定名 | 機能 | リンクなど |
| ---- | ---- | ---- |
| ecmaVersions | 使用するECMAScript構文のversionを指定 ||
| sourceType | コードがECMAScript ||
| ecmaFeatures | 使用する追加の言語機能 ||
### env
静的検証の前提条件を設定
| 設定名 | 機能 | リンクなど |
| ---- | ---- | ---- |
| es6 | モジュールを除くすべてのES6機能を有効 ||
### globals
スクリプトが実行中にアクセスする追加のglobal変数
| 設定名 | 機能 | リンクなど |
| ---- | ---- | ---- |
||||
### rules
コードを検証するための条件
| 設定名 | 機能 | リンクなど |
| ---- | ---- | ---- |
| semi | 文末にはセミコロンを記述すること ||
### ignorePatterns
無視するファイル形式等
| 設定名 | 機能 | リンクなど |
| ---- | ---- | ---- |
||||

## {react_project}/.prettierrc.json
| 設定名 | 機能 | リンクなど |
| ---- | ---- | ---- |
| tabWidth | インデントレベルをスペ－スで指定 ||
| semi | 文章の雑賀にセミコロンを表示 ||
| singleQuote | ダブルクオーテーションの代わりにシングルクオーテーションを使用 ||
| trailingComma | カンマで区切られた複数行の構文構造で、可能な限り文末にカンマを表示 ||

## 備考
- https://eslint.org/
- https://prettier.io/