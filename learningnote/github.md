# ubuntu project推送

ssh keys创建

```bash
 ssh-keygen -t rsa -C "stone1987killer@gmail.com"
```

本地生成的 keys位置：

```bash
cd /root/.ssh/
more id_rsa.pub
```

```
 打开id_rsa.pub，复制加密的内容： 

 到GitHub上创建SSH keys，点击”New SSH Key”： 

 取个名字，并把复制的加密内容粘贴进去：
```

 验证 SSH Keys 是否添加成功 

```bash
 ssh -T git@github.com 
```

 进行全局配置 

```bash
git config --global user.name 'sl6731220'
git config --global user.email 'stone1987killer@gmail.com'
```

本地创建的project文件夹docsifysl，并克隆github上的仓库到sl文件夹

```bash
cd docsifysl/
git clone git@github.com:sl6731220/sl.git
```

推送codes

```bash
 git pull
```

 查看状态 

```bash
 git status
```

 将所有变动文件提交到暂存区 

```bash
git add .
```

 将变动文件提交至本地仓库 

```bash
git commit -m "init project"
```

 连接远程GitHub仓库项目 

```bash
git remote add origin git@github.com:sl6731220/sl.git
```

 将本地仓库项目更新提交到GitHub仓库项目中 

```bash
 git push -u origin master
```



# window10  推送

安装git

指定文件夹-----打开cmd------git clone http：sl

cd sl -------git status

更新：

git add 或者 git add *全部

git commit -m "更新说明“

config:

找到上传项目目录的.git文件夹，打开之后找到config文件，在最后边加上一句话
[user]
email=your email
name=your name



[reference](https://www.jianshu.com/p/803be5f58caf)