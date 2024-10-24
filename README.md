# ElasticのLtRを試してみる

ElasticのLtRをローカルで試してみるためのJupyter notebookです。
DockerでElasticsearch、Kibana、Jupyter notebookを起動して確認できます。

## 準備

docker composeで2つのコンテナを起動します（Kibanaを利用する場合はkibanaも）

```
docker compose up es815 jupyter kibana
```

ブラウザで[http://localhost:8888](http://localhost:8888)にアクセスするとJupyterLabにアクセスできます。

`notebooks/hello-elastic-ltr-basedon-elasticsearch-labs.ipynb`がElasticのLtRを実行するためのノートブックです。


## 内容物

* docker-compose.yml：
* es-docker：o19sのLtRプラグインを試すためのElasticsearchのDockerファイル
* notebooksディレクトリ：Jupyter notebookファイル
* restディレクトリ：VS CodeのREST clientを利用して接続確認などをするためのrestファイル
* .devcontainer：Devcontainerの設定など
* .devcontainer/Dockerfile：JupyterLab用のコンテナのDockerファイル

### LtRとは？

#### Learning to Rank (LtR)の基本概念

Learning to Rankは、検索結果のランキングを機械学習を用いて最適化する手法です。

**主な特徴：**

- 複数の特徴量（features）を組み合わせて最適なランキングを学習
- クリックログやユーザーフィードバックなどの教師データを使用
- 検索結果の関連性をスコア化して順位付け

**一般的なLtRの処理フロー**

- 特徴量の抽出：文書の長さ、単語の一致度、PageRankなど
- モデルの学習：教師データを使用して最適な重みを学習
- 予測：新しい検索クエリに対してランキングを適用


## VSCode + Dev Containerの利用

VSCodeのDev Container拡張を利用することで、VSCode上でJupyter notebookを動作させながら編集することもできます。

## ライセンス

[LICENSE](./LICENSE)ファイルを参照のこと


## 謝辞

[https://github.com/elastic/elasticsearch-labs/blob/main/notebooks/search/08-learning-to-rank.ipynb](https://github.com/elastic/elasticsearch-labs/blob/main/notebooks/search/08-learning-to-rank.ipynb)のサンプルをもとにさせていただきました。

