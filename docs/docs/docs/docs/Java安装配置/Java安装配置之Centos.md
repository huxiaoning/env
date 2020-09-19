##### Java安装配置之Centos



```bash
$ vim /etc/profile.d/java.sh
export JAVA_HOME=/opt/Java/jdk-11.0.8
export PATH=$JAVA_HOME/bin:$PATH
export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
```

