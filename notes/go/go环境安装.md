=======================搭建虚拟机ubantu===================
1 安装vbox虚拟机
2 使能cpu虚拟化技术(进bios修改)
3 安装ubantu系统

=======================go安装=======================
1 下载源码 http://www.golangtc.com/download
2 解压源码到安装目录(例:/usr/local) tar -xzf xxx.go /usr/local
3 导出go环境变量， 编辑$HOME/.profile文件，尾部添加如下行：
  export GOROOT=/usr/local/go  #go安装目录
  export GOBIN=$GOROOT/bin
  export GOARCH=amd64
  export GOOS=linux
  export GOPATH=$HOME/go
  PATH=$PATH:$GOBIN
4 cd /usr/local/go/src  执行 ./all.bash

=========================vim go ide==========================
1 mkdir -p ~/.vim/bundle
2 cd ~/.vim/bundle 执行 git clone https://github.com/VundleVim/Vundle.vim   
3 替换.vimrc配置文件 重起vim 执行:PluginInstall  :PluginInstallBinaries   
4 sudo apt-get install vim-nox    在.vimrc中添加 'Plugin Showgo/neocomplete.vim'

=========================ubantu 中文输入法=================
1 software center 安装 fictx
2 设置-->语言支持-->中文
3 状态栏右侧最左边那个图标，点击选择配置输入法，添加中文输入法即可

===========================git项目库搭建===========================
1 root 创建respo   cd respo && git --bare
2 修改respo权限 使同组用户具有写权限，便于多人共同开发提交  chmod 771 respo
3 添加同组用户  useradd -m -G root test
4 创建本地库并添加远程库 git init xxx  && git remote add origin ssh://test@xxx.xxx.xxx.xxxx/xxx/respo
5 git相关开发操作

============================go net包安装=========================
1 mkdir -p $GOPATH/golang.org/x    
2 cd $GOPATH/golang.org/x && git clone https://github.com/golang/net

===========================ubantu install mondb=========================
1 sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
2 echo "deb http://repo.mongodb.org/apt/ubuntu "$(lsb_release -sc)"/mongodb-org/3.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb.list  
3 sudo apt-get update
4 sudo apt-get install mongodb-org
5 apt-get install mongodb-org=3.0.0 mongodb-org-server=3.0.0 mongodb-org-shell=3.0.0 mongodb-org-mongos=3.0.0 mongodb-org-tools=3.0.0
6 sudo service mongod start
  sudo service mongod stop
  mongo --version
7 sudo vim /var/log/mongodb/mongod.log
ps:http://tecadmin.net/install-mongodb-on-ubuntu/      http://my.oschina.net/quanpower/blog/282546

===========================ubantu install redis============================
1 sudo apt-get update
2 $sudo apt-get install redis-server   
	
===========================ubantu install nsq==============================
1 git clone https://github.com/pote/gpm.git && cd gpm
2 ./configure && make install
3 git clone https://github.com/nsqio/nsq.git  && cd nsq
4 gpm install
5 ./test.shell  
6 go get ...   // 安装nsq
ps:上述git操作请在GOPATH目录下进行，否则会产生go build不过问题

===========================ubantu install mysql============================
1 sudo apt-get install mysql-server mysql-client
2 sudo service mysql restart

============================提升non-sudo的sudo能力===============================
1 su -
2 visudo 或 chmod u+w /etc/sudoers  vim sudoers
3 添加此行 username     ALL=(ALL)  ALL  // 可仿照root添加


## vim-go安装
*[博客](http://www.cnblogs.com/yuuyuu/p/5222980.html)


   
