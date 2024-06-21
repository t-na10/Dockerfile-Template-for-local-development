# devcontainerのテンプレートについて

devcontainerのテンプレートです。vscodeの拡張機能であるRemote - Containersを使用して、開発環境を構築する際には、このテンプレートを使用してください。

## カスタマイズ
devcontainer.jsonには、以下の設定が記載されています。
- name: コンテナ名
- dockerfile: Dockerfileのパス


使用するコンテナ名やDockerfileのパスを変更する場合は、`devcontainer.json`を編集してください。


### VSCode 拡張機能と設定

#### 拡張機能

- **MS-CEINTL.vscode-language-pack-ja**: VSCodeの日本語言語パック。VSCodeのUIを日本語にする。
- **ms-azuretools.vscode-docker**: Dockerの統合。コンテナの管理や操作をVSCode内で行う。
- **GitHub.vscode-pull-request-github**: GitHub Pull RequestsとIssuesの統合。VSCode内でPull RequestやIssueの操作を行う。
- **eamodio.gitlens**: GitLens - Gitの拡張機能。リポジトリの詳細な履歴やブレーム情報を提供。
- **mhutchie.git-graph**: Git Graph - Gitリポジトリのグラフ表示。リポジトリのブランチ構造を視覚的に表示。
- **ms-toolsai.jupyter**: Jupyterノートブックの統合。VSCode内でJupyterノートブックを作成、編集、実行。
- **ms-toolsai.vscode-jupyter-cell-tags**: Jupyterセルタグのサポート。セルにタグを追加して管理。
- **ms-toolsai.jupyter-keymap**: Jupyterノートブックのキーマップ。VSCodeのキーボードショートカットをJupyterノートブックに適用。
- **ms-toolsai.jupyter-renderers**: Jupyterノートブックのレンダリング拡張。VSCode内でのデータビジュアライゼーションの改善。
- **ms-toolsai.vscode-jupyter-slideshow**: Jupyterノートブックのスライドショー作成。ノートブックをプレゼンテーション形式に変換。
- **ms-python.python**: Python拡張機能。Pythonコードの補完、デバッグ、Linting、フォーマットをサポート。
- **ms-python.vscode-pylance**: Pylance - 高速で正確なPython言語サーバー。
- **KevinRose.vsc-python-indent**: Pythonインデントのサポート。Pythonコードのインデントを自動調整。
- **njpwerner.autodocstring**: Python Docstringの自動生成。関数やクラスにドキュメンテーションを追加。
- **ms-python.flake8**: Flake8 - PythonのLinting。コードのスタイルとエラーチェック。
- **ms-python.isort**: isort - Pythonのインポート順序整理。インポートステートメントの順序を整理。
- **shardulm94.trailing-spaces**: Trailing Spaces - 末尾の空白をハイライト。不要な空白を削除。
- **oderwat.indent-rainbow**: インデントの可視化。異なるインデントレベルを色分け。
- **Gruntfuggly.todo-tree**: TODO Tree - TODO、FIXMEなどのタグをツリー表示。コード内のタスク管理。

#### 設定

- **[python]**: Pythonファイルに対するエディター設定。
  - `editor.defaultFormatter`: `ms-python.black-formatter` - PythonコードのフォーマッターをBlackに設定。
  - `editor.formatOnSave`: true - ファイル保存時に自動フォーマットを実行。
  - `editor.formatOnPaste`: true - ペースト時に自動フォーマットを実行。
  - `editor.formatOnType`: true - タイプ時に自動フォーマットを実行。
  - `files.trimTrailingWhitespace`: true - ファイル保存時に末尾の空白を自動で削除。
  - `files.insertFinalNewline`: true - ファイル保存時に末尾に改行を追加。

- **flake8.args**: Flake8の設定。
  - `--max-complexity=10` - 複雑度の最大値を10に設定。
  - `--max-line-length=127` - 行の最大長を127文字に設定。
  - `--extend-ignore=E203,DOC301` - 無視するエラーコードを追加。

- **black-formatter.args**: Blackフォーマッターの設定。
  - `--line-length=127` - 行の最大長を127文字に設定。

- **isort.args**: isortの設定。
  - `--profile=black` - Blackのプロファイルを使用。
  - `--line-length=127` - 行の最大長を127文字に設定。

- **editor.codeActionsOnSave**: 保存時のコードアクション設定。
  - `source.organizeImports`: "explicit" - 保存時にインポートを整理。

- **notebook.formatOnSave.enabled**: ノートブックの保存時フォーマットを有効化。
