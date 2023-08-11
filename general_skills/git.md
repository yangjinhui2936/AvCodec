
# git 使用教程
<!-- TOC -->

- [git 使用教程](#git-%E4%BD%BF%E7%94%A8%E6%95%99%E7%A8%8B)
    - [github关联本地server提交代码](#github%E5%85%B3%E8%81%94%E6%9C%AC%E5%9C%B0server%E6%8F%90%E4%BA%A4%E4%BB%A3%E7%A0%81)
        - [从github关联linux服务器](#%E4%BB%8Egithub%E5%85%B3%E8%81%94linux%E6%9C%8D%E5%8A%A1%E5%99%A8)
            - [github中新建工程](#github%E4%B8%AD%E6%96%B0%E5%BB%BA%E5%B7%A5%E7%A8%8B)
            - [本地安装git工具](#%E6%9C%AC%E5%9C%B0%E5%AE%89%E8%A3%85git%E5%B7%A5%E5%85%B7)
            - [关联账户](#%E5%85%B3%E8%81%94%E8%B4%A6%E6%88%B7)
            - [git clone到本地](#git-clone%E5%88%B0%E6%9C%AC%E5%9C%B0)
            - [设置ssh key](#%E8%AE%BE%E7%BD%AEssh-key)
            - [添加修改文件到本地server](#%E6%B7%BB%E5%8A%A0%E4%BF%AE%E6%94%B9%E6%96%87%E4%BB%B6%E5%88%B0%E6%9C%AC%E5%9C%B0server)
            - [切到GitHub上merge即可](#%E5%88%87%E5%88%B0github%E4%B8%8Amerge%E5%8D%B3%E5%8F%AF)
    - [git 常用命令](#git-%E5%B8%B8%E7%94%A8%E5%91%BD%E4%BB%A4)

<!-- /TOC -->

## github关联本地server提交代码
 ### 从github关联linux服务器  
 #### github中新建工程
   打开github.com并add project
 #### 本地安装git工具
   ```shell
   Debian/Ubuntu
   For the latest stable version for your release of Debian/Ubuntu

   # apt-get install git
   For Ubuntu, this PPA provides the latest stable upstream Git version

   # add-apt-repository ppa:git-core/ppa # apt update; apt install git
   ```
#### 关联账户
```shell
   git config --list 查看信息
   git config user.email 
   git config user.name 
```

 #### git clone到本地   
   ```shell
   git clone https://github.com/yangjinhui2936/AvCodec.git`
   `git remote add origon https://github.com/yangjinhui2936/AvCodec.git
   ```
#### 设置ssh key
    ssh-keygen -t rsa -C "邮箱地址"
    将~/.ssh 目录下id_rsa id_rsa.pub 内容复制到 github中是SSH and GPG keys 中，需要新建New SSH key
    1. 测试是否成功连接GitHub
    `ssh -T git@github.com `
    2. 提示`git@github.com: Permission denied (publickey)`
      chmod 600 ~/.ssh/*
#### 添加修改文件到本地server
```shell
git add .
git commit -m "frist commit"
git push -u origin master
git branch //可查看当前分支 
//如果不在master可使用：
git checkout master
```
#### 切到GitHub上merge即可 
  ##  git 常用命令
  ```shell
  git remote -v   //查看远程地址

  ```