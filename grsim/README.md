
# grSim

[RoboCup-SSL/grsim](https://github.com/RoboCup-SSL/grSim)
を実行するためのDockerfile

## Build

`build.sh`を実行すると`grsim:latest`というイメージが生成されます

```sh
$ ./build.sh
...
Successfully tagged grsim:latest
```

## Usage

```sh
# ホストにgrSimの設定ファイルを生成
$ touch .grsim.xml

# grSimを起動
$ rocker --x11 --net=host --volume .grsim.xml:/root/robocup/.grsim.xml -- grsim:latest ./grSim

# clientを起動
$ rocker --x11 --net=host grsim:latest ./client
```
