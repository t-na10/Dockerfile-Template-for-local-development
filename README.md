<div align="center">

# Dockerfile Template for local development


</div>

ローカル開発用のDockerfileテンプレートです。Pythonの開発環境を構築するためのDockerfileを提供しています。


## ディレクトリ構成
```
.
├── README.md
└── docker
    ├── Dockerfile
    ├── requirements.txt
    ├── tensorflow
    │   ├── Dockerfile
    │   └── requirements_mac.txt
    └── torch
        ├── Dockerfile
        └── requirements.txt
```
## ファイル構成
以下の3種類のDockerfileを提供しています。
1. Pythonの開発環境を構築するためのDockerfile（flake8, ipykernel, ipywidgets, python-dotenv, jupyterのみの状態）
    - `./docker/Dockerfile`
    - `./docker/requirements.txt`
2. TensorFlow＋MLライブラリを使用するためのDockerfile
    - `./docker/tensorflow/Dockerfile`
    - `./docker/tensorflow/requirements_mac.txt`
3. PyTorch＋MLライブラリを使用するためのDockerfile
    - `torch/Dockerfile`
    - `torch/requirements.txt`


## 実行方法

### 1. Pythonの開発環境を構築するためのDockerfile

#### Dockerイメージのビルド

```
docker build -t <イメージ名> -f docker/Dockerfile docker/
```

#### Dockerコンテナの起動

```
docker run --rm -it -v $(pwd):/work -w /work <イメージ名>
```

### 2. TensorFlow＋MLライブラリを使用するためのDockerfile

#### Dockerイメージのビルド

```
docker build -t <イメージ名> -f docker/tensorflow/Dockerfile docker/tensorflow/
```

#### Dockerコンテナの起動

```
docker run --rm -it -v $(pwd):/work -w /work <イメージ名>
```


### 3. PyTorch＋MLライブラリを使用するためのDockerfile

#### Dockerイメージのビルド

```
docker build -t <イメージ名> -f docker/torch/Dockerfile docker/torch/
```

※ Apple Silicon Macを使用している方へ
- 以下のコマンドでビルドしてください。
    ```
    docker build --platform linux/amd64 -t <イメージ名> -f docker/torch/Dockerfile docker/torch/
    ```

#### Dockerコンテナの起動

```
docker run --rm -it -v $(pwd):/work -w /work <イメージ名>
```