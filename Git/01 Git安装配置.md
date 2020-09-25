##### 生成密钥对

```shell
$ sudo apt update
$ sudo apt install -y git
$ git --version
$ git config --global user.name "huxiaoningsworld"
$ git config --global user.email "huxiaoningsworld@sina.com"
$ ssh-keygen -t rsa -C "huxiaoningsworld@sina.com"
$ cat ~/.ssh/id_rsa.pub
```



##### GitHub端口配置和代理配置

```shell
$ cat ~/.ssh/config
Host xxxx.com
        port xxx
        IdentityFile C:\Users\aidan\.ssh\id_rsa
Host ssh.github.com
        User    git
        Hostname        ssh.github.com
        Port    443
        ProxyCommand    connect -S 127.0.0.1:60002 -a none %h %p
        IdentityFile C:\Users\aidan\.ssh\id_rsa
 Host github.com
        User    git
        Hostname        github.com
        Port    22
        ProxyCommand    connect -S 127.0.0.1:60002 -a none %h %p
        IdentityFile C:\Users\aidan\.ssh\id_rsa
```



##### 常用别名

```shell
$ alias add='git add .'
$ alias commit='vim ~/info.txt && git commit -m "$(cat ~/info.txt)"'
$ alias pull='git pull'
$ alias push='git push'
$ alias status='git status'
```

