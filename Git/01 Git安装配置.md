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

