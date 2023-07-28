## git 使用教程

### github关联本地server提交代码
 #### 从github中开始
 1. github中新建工程
 2. 本地安装git工具
    ``` shell
    Debian/Ubuntu
    For the latest stable version for your release of Debian/Ubuntu

    # apt-get install git
    For Ubuntu, this PPA provides the latest stable upstream Git version

    # add-apt-repository ppa:git-core/ppa # apt update; apt install git
    ```
 3. git clone到本地
    `git clone https://github.com/yangjinhui2936/AvCodec.git`
    `git remote add origon https://github.com/yangjinhui2936/AvCodec.git`
 4. 设置ssh key
    ssh-keygen -t rsa -C "邮箱地址"
    将~/.ssh 目录下id_rsa id_rsa.pub 内容复制到 github中是SSH and GPG keys 中，需要新建New SSH key
 1. 测试是否成功连接GitHub
    `ssh -T git@github.com `
