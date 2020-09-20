##### 自动生成`Summary.md`目录(持续更新中...)

```shell
# 用Java写了个程序(目前没有开源) gitbook-helper-1.0-SNAPSHOT.jar
$ java -jar -Dwork.dir=C:\Users\Jett\Documents\env target/gitbook-helper-1.0-SNAPSHOT.jar
```



用起来很不方便,做一个docker镜像吧

```shell
$ vim Dockerfile
FROM centos:7
ADD jdk-8u261-linux-x64.tar.gz /opt/Java/
ENV JAVA_HOME=/opt/Java/jdk1.8.0_261 \
	PATH=/opt/Java/jdk1.8.0_261/bin:$PATH \
	CLASSPATH=.:/opt/Java/jdk1.8.0_261/lib/dt.jar:/opt/Java/jdk1.8.0_261/lib/tools.jar
COPY gitbook-helper-1.0-SNAPSHOT.jar /

# 中文筹码处理，参考(https://blog.csdn.net/wo541075754/article/details/89787894)
RUN yum install -y kde-l10n-Chinese glibc-common
RUN localedef -c -f UTF-8 -i zh_CN zh_CN.utf8
RUN export LANG=zh_CN.UTF-8
RUN echo "export LANG=zh_CN.UTF-8" >> /etc/locale.conf
ENV LANG zh_CN.UTF-8
ENV LC_ALL zh_CN.UTF-8

WORKDIR /work/
CMD [ "java","-jar","-Ddocker=1","/gitbook-helper-1.0-SNAPSHOT.jar" ]

$ docker rmi gitbook-helper:1.0
$ docker build -t gitbook-helper:1.0 .

# 仅能在windows powershell环境下调试
$ docker run --rm -it -v /c/Users/Jett/Documents/env:/work/ gitbook-helper:1.0 bash
$ java -jar -Ddocker=1 /gitbook-helper-1.0-SNAPSHOT.jar

# 正试的语句,一定要在gitbash环境下执行 (没有成功，目录没有挂载上去)
$ winpty docker run --rm -it -v "$(pwd):/work/" gitbook-helper:1.0
```

