# Docker-jupyterlab-Template

Dockerを使って、自分のPCにjupyterlabの環境構築を行う方法を紹介する。

前提として、[Docker](https://www.docker.com/products/docker-desktop)がインストールされていることが必要である。

## Usage

### Windows

もしDockerのインストールにこける場合は、[ここ](https://docs.docker.com/desktop/windows/release-notes/)から古いDocker Desktopをインストールすれば解決すると思う。
自分は、PC自体が古いので [Docker Desktop for Windows2.5.0.0](https://docs.docker.com/desktop/windows/release-notes/2.x/)をインストールしている。

### Ubuntuの場合

aptで、docker, docker-compseをインストールする

```bash
sudo apt install docker
sudo apt install docker-compose
```

### 手順

さて起動方法だが、コマンドプロンプトを開いて、このレポジトリをダウンロードしたディレクトリまで移動する。移動したら、下記のコマンドを打ち込む

```bash
# 移動
cd Docker-jupyterlab-Template

# jupyterlabの起動(Ubuntuの場合は、sudoをつけて実行すること)
docker-compose up -d
```

最初は初期構築のために時間がかかるが、一回やってしまえばその後はやらないので我慢してください。

下記の出力が返ってくれば、構築が完了している。

```
Creating docker-jupyterlab-template_notebook_1 ... done
```

次に[http://localhost:8888](http://localhost:8888)にアクセスすれば、jpupyterlabのブラウザ画面が開かれるはずである。

jupyterlabの開始方法の次は停止方法である。
以下のコマンドを打てば止まるはずである。

```bash
docker-compose stop
```

またjupyterlabを始める際には、以下のコマンドを打てばよい。

```bash
docker-compose start 
```

忘れないで欲しいのが、ちゃんとdocker-compose.ymlがあるディレクトリで実行すること!!!

もうこのjupyterlabを使わないのであれば、以下のコマンドを入力してください。

```bash
docker-compose down
docker rmi jupyter/datascience-notebook
```

## 参考サイト

- [【Docker】3分でjupyterLab(python)環境を作る！](https://qiita.com/hgaiji/items/edf71435d0565257f980)

