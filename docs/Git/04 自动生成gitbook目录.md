##### 自动生成`Summary.md`目录(持续更新中...)

```shell
# 用Java写了个程序(目前没有开源) gitbook-helper-1.0-SNAPSHOT.jar
$ java -jar -Dwork.dir=C:\Users\Jett\Documents\env target/gitbook-helper-1.0-SNAPSHOT.jar
```



用起来很不方便,做一个docker镜像吧

```shell
$ vim Dockerfile
FROM centos:7
ADD jdk-8u261-linux-x64.tar.gz /opt/
ENV JAVA_HOME=/opt/Java/jdk-11.0.8 \
	PATH=$JAVA_HOME/bin:$PATH \
	CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar

$ docker build -t gitbook-helper:1.0 .
$ docker run --rm -it gitbook-helper:1.0 bash
```

