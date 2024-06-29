# Docker

### 启动
```
service docker start
```

### 构建
```
docker-compose build
```

### 创建并启动容器
```
docker-compose up -d
```

### 开启服务
```
docker-compose start
```

### 查看容器
```
正在运行的容器：docker ps

所有容器：docker ps -a

容器id：docker ps -a -q
```

### 关闭容器
```
关闭一个容器：docker stop containerId

关闭所有容器：docker stop $(docker ps -a -q)
```

### 删除容器
```
docker rm $(docker ps -a -q)
```

### 查看镜像
```
docker images -a
```

### 删除镜像
```
docker rmi $(docker images -a -q)
```
