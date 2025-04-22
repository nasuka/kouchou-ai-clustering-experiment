# kouchou-ai-clustering-experiment

広聴AIフレームワークを使用した階層的クラスタリング実験のためのワークスペースです。

このリポジトリには、コメントデータの階層的クラスタリングとAI駆動のラベリングを評価・改良するためのデータセット、プロンプト、ノートブック、および広聴AIコードベースが含まれています。

## クローン方法

このリポジトリにはサブモジュールが含まれているため、以下のコマンドを使用して完全にクローンしてください：

```bash
git clone --recurse-submodules https://github.com/nasuka/kouchou-ai-clustering-experiment.git
```

既にリポジトリをクローンしている場合は、以下のコマンドでサブモジュールを初期化・更新できます：

```bash
git submodule init
git submodule update
```

**注意**: サブモジュールなしでクローンした場合、`kouchou-ai`ディレクトリが空になり、プロジェクトが正常に動作しません。

## 環境セットアップ

このプロジェクトはPython 3.12以上が必要です。依存関係をインストールするには：

```bash
rye sync
```


## リポジトリ構造

- data/
  - inputs/: クラスタリング実験用のCSVデータセット
  - original_outputs/: 広聴AIパイプラインによって生成されたベースライン出力
  - experiment_outputs/: 比較のための修正プロンプト実験の結果
  - pubcom_inputs/: パブリックコメントデータ
  - pubcom_outputs/: パブリックコメント実験の結果
- notebooks/: プロンプト調整と自動評価ワークフローを示すJupyterノートブック
- prompts/: クラスタタイトル評価とラベリングタスクに使用されるテキストプロンプト
- kouchou-ai/: 主要な広聴AIフレームワーク（サブモジュール）
  - client/: Next.jsベースのレポートビューア
  - client-admin/: データセットアップロードとレポート作成のための管理インターフェース
  - server/: FastAPIバックエンドと階層的クラスタリングパイプライン
  - utils/: ユーティリティスクリプトとダミーサーバー
  - docs/ および how_to_use/: 詳細な使用ガイドとドキュメント
- pyproject.toml, requirements.lock, requirements-dev.lock: Python依存関係とプロジェクト設定

## 使用方法

* このリポジトリは主に階層的クラスタリングアルゴリズムの実験と評価のために使用されます。Jupyterノートブックを通じて実験を実行できます。
* notebookは全てVS Code上で動かしています。jupyte notebookの起動方法・場所によっては、pathが異なり、packageのimportやファイルの読み込みに失敗することがあります。