# docker

## docker infor：

```
docker version

systemctl status docker 

docker info
```



## 创建：

```
docker run -itd -v xxx:xxx -p xxx:xxxx id
```

## 启动：

```
docker exec -it  xxx bash
```

```
docker attach xxx
```

## 关闭：

```python
exit//容器内
```

```
docker stop id
```

```dart
docker stop $(docker ps -a | awk '{ print $1}' | tail -n +2)
```

## 网络:

```bash
docker network create -d bridge my-net
```

```bash
docker run -itd --rm --name hadoop1 --network my-net containerid
```

## docker守护态运行

```
Ctrl+P+Q
```

## docker查看information

```
docker info
```

## docker images删除

```
docker rmi imageID
docker rmi -f  imageid
```

## docker container 删除

```dart
docker rm $(docker ps -a | awk '{ print $1}' | tail -n +2)
```

