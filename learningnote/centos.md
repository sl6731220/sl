centos

```bash
cd /etc/
```

```bash
#放开文件sudoers全部权限
chmod  777  sudoers
```

```bash
配置：
#原有
root    ALL=(ALL:ALL) ALL
#添加
sl  ALL=(ALL:ALL) ALL
```

ubuntu

```bash
vim /etc/passwd
```

修改用户id和组id 都为0

## 修改主机名

```
hostnamectl set-hostname sl
```

```
hostname
```

ssh 登录

```bash
$ s
```

```
PermitRootLogin no->PermitRootLogin yes 
```

```bash
$ sudo service ssh restart 
```

## 我是谁

```bash
whoami //登录权限
who mom likes
```

