```shell
$ npm install gitbook-cli -g
```

```shell
# 初始gitbook
$ gitbook init
# 构建站点静态资源 _book/ 目录
$ gitbook build
# 启动一个服调试站点
$ gitbook serve

# 安装插件
$ gitbook install
```

###### `gitbook init`报错 cb.apply is not a function 问题处理

```
https://flaviocopes.com/cb-apply-not-a-function/
```


##### 常用别名

```shell
# 自动生成目录
$ ...还没研究好
# 一键提交
$ alias up='rm -rf _book && gitbook build && rm -rf docs && mv _book docs && git add . && git commit -m "UP" && git push'
```

##### 自动提交脚本

```shell
# 记得把C:\developerInstall\bin配置环境变量PATH中
$ vim /c/developerInstall/bin/up
#!/bin/bash
rm -rf _book docs
gitbook build
mv _book docs
git add .
git commit -m "UP"
git push
$ chmod.exe 755 /c/developerInstall/bin/up
```




