[TOC]

# git bash SSH 连通远程仓库

### 申请github账户 <https://github.com>

### 下载安装Git， gitbash

### 生成ssh秘钥

1. 打开gitbash

![1536386561198](C:\Users\wenhui\AppData\Local\Temp\1536386561198.png)

2. 生成SSH秘钥，地址是<C:\Users\wenhui\.ssh>

### 打开id_rsa.pub， 拷贝公钥内容

### 登陆github.com，打开settings> ssh and GPGs>新建sshkey

### gitbash内： `ssh -T git@github.com` 测试连通

### git 添加远程origin:

```
git remote add origin git@github.com:shangxiagithub/techMiscellaneous.git
```



#### 注意，我在github上添加完成公钥之后，bash内测试连通一直失败的root cause

> permission denied(Public Key)

`ssh-keygen`的时候，提示指定秘钥文件名称，我都自定义了名称，所以生成的公钥文件名就成了：

> zwh
>
> zwh.pub

这样屡次测试都失败，提示以上错误信息，应该是git连通是使用默认密钥名称，如果自定义，则无法解析找到密钥，默认密钥名称是：

> id_rsa.pub
>
> id_rsa

*end*



