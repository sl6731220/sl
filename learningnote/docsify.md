docsify部署：

```bash
git init
git add .
git commit -m 'docsify项目初始化'
git remote add origin https://github.com/username/docsify.git
git push --set-upstream origin master
```

 打开github的仓库，选择`Settings` -> `GitHub Pages` -> `master branch` -> `save` 

github pages:

master branch

GitHub Pages 支持从三个地方读取文件:

> 1、`master`分支
> 2、`master`分支下的`docs`目录
> 3、`gh-pages`分支

> 1、如果你的文档直接是在项目根目录写的，那么可直接把代码推送到master分支上， `GitHub Pages`里选择`master branch`.
> 2.如果你的文档是在master分支下的`docs/`目录下编写的，那么可直接把代码推送到master分支上，`GitHub Pages`里选择`master branch/docs folder`.

本例子项目是直接在根目录中编写的，所以`GitHub Pages`里选择`master branch`的方式部署。

