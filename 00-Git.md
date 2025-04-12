# Git

下载Git，初始化配置：

```sh
git config --global user.name "<GitHub用户名>"
git config --global user.email "<Github邮箱>"
```

进入文件夹：

```sh
git init
git add .
git commit -m "Initial commit: xxx"
```

在Github新建仓库，不选初始带有README，复制仓库的HTTPS或SSH，关联本地仓库和远程仓库：

```sh
git remote add origin git@github.com:<用户名>/<仓库名>.git
```

首次推送：

```sh
git push -u origin master  # 首次推送需加 `-u`
```

后续常规：

修改或新增文件后，在终端执行：

```sh
git add .
git commit -m "更新内容描述"
git push
```



