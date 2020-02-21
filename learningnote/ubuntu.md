# ubuntu

## 修改环境变量

```
vim ~/.bashrc
export PATH=$PATH:/home/sl/anaconda3/bin
source ~/.bashrc
conda info --envs
```

##  查看ip

```bash
ip a
```

##  配置静态ip

``` bash
sudo netplan generate 
```

 ```bash
sudo vim /etc/netplan/xxxx.ymal 
 ```

```
配置：
network:
    ethernets:
        ens33:
             addresses:
             - 192.168.189.130/24
             dhcp4: false
             gateway4: 192.168.130.1
             nameservers:
                 addresses:
                 - 8.8.8.8
                 search: []
    version: 2
```

``` bash
sudo netplan apply
```

[参考]: https://www.jb51.net/article/151753.htm

##  添加sudo权限

``` bash
#添加组
groupadd dockergroup
```

```bash
#保持原先的组属性并添加到新组
usermod -aG dockergroup sl
```

```bash
#sudoers文件只能读不能修改
vim /etc/sudoers
```

