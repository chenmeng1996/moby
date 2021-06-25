## 创建镜像，并创建容器，并进入
```bash
make BIND_DIR=. shell
```
## 修改本地代码，因为mount到容器，所以自动同步到容器内
pass
## 在容器内编译，并将可执行二进制文件复制到/usr/bin
```bash
hack/make.sh binary install-binary
```
## 在容器内运行dockerd
```bash
dockerd -D &
```
## 测试
```bash
docker run hello-world
```
## 再次创建容器，并进入
```bash
docker run --privileged --rm -it -v `pwd`:/go/src/github.com/docker/docker docker-dev:chenmeng /bin/bash
```