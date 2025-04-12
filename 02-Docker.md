# Docker

#### upgrade docker

```Sh
sudo apt update
sudo apt update
sudo apt full-upgrade
```

#### show images

```sh
sudo docker images
```

#### download images

```sh
sudo docker pill ubuntu
```

#### run docker

```sh
sudo docker run -it ubuntu:<TAG> --name <Name> /bin/bash
```

- `-t`：在 Ubuntu 容器内分配一个伪终端。
- `-i`：通过从容器获取一个标准输入（STDIN），允许我们创建一个可交互的连接。
- `ubuntu:latest`：标签为 `latest` 的 Ubuntu Docker 镜像。
- `/bin/bash`：新容器的 BASH shell。这个是可选项。如果你不加 shell 的话，会分配默认的 shell 给容器。

#### detach docker terminal

```
Ctrl+P, Ctrl+Q
```

#### show container status

```sh
docker ps [-a]
```

`-a`：显示所有容器，包括已停止的等等。

#### attach docker terminal

```sh
sudo docker attach <container-id|name>
```

#### start/stop/pause/unpause/remove docker

```sh
sudo docker start/stop/pause/unpause/rm <name>
# stop a container in the docker's shell
exit
```

#### rename

```sh
sudo docker rename <raw-name> <new-name>
```

























