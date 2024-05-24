# ローカル開発用Docker環境

## Apple Silicon MacでPythonを使用する方へ

ライブラリの互換性のため、Dockerfileが2通りに分かれています。次のようにイメージをビルドしてください。

### PyTorchを使わない場合

次のように、 `Dockerfile_mac` を使用して --platform を指定せずにビルドしてください。
```
$ docker build -t local_ -f docker/python/Dockerfile_mac docker/python
```

この環境では、PyTorchは正常にインストールできないため除かれています。

### PyTorchを使う場合

次のように、 `Dockerfile_mac_torch` を使用してビルドしてください。
```
$ docker build --platform linux/amd64 -t local_tester -f docker/python/Dockerfile_mac_torch docker/python
```

この環境では、TensorFlowは正常に動作しないため除かれています。