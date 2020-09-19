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



##### 常用别名

```shell
# 自动生成目录
$ ...还没研究好
# 一键提交
$ alias up='rm -rf _book && gitbook build && rm -rf docs && mv _book docs && git add . && git commit -m "UP" && git push'
```



###### `gitbook init`报错 cb.apply is not a function 问题处理

```
https://flaviocopes.com/cb-apply-not-a-function/
```



##### 自动生成目录

```
https://www.cnblogs.com/luoheng23/p/11197922.html
https://blog.csdn.net/dianguanding1120/article/details/101718406
```

