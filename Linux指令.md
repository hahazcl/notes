# Linux指令

- #### 基本指令

  ```bash
  ssh -R 20000:localhost:端口号 ip地址  # 与另一个ip建立隧道
  rm  -rf 文件夹 # 强制删除文件夹
  mkdir 文件名 # 新建文件夹
  mkdir aa/bb/cc -p # 创建有依赖的文件夹aa/bb/cc
  cd .. # 返回上一个目录
  cd .  # 切换到当前目录
  cd -  # 切换到上一次目录
  pwd   # 查看当前路径
  clear # 清屏
  cp 被复制文件夹 目标文件夹 -r # 递归复制文件夹下面的所有文件到新文件夹
  cp 文件路径/* 新文件夹 # 复制文件夹下面的所有文件到新文件夹里面
  mv 文件名 同目录下不存在的文件夹名 # 将文件夹重命名
  命令 --help # 查看命令的选项信息
  find 指定文件目录下 -name 文件名称  # 在指定目录下查找指定文件的文件路径
  ---------------------------------
  man 命令 # 查看命令帮助信息
  ```

  | 操作符 |      说明      |
  | :----: | :------------: |
  |  空格  | 显示上一行信息 |
  |  回车  | 显示下一行信息 |
  |   b    | 显示上一屏信息 |
  |   f    | 显示下一屏信息 |
  |   q    |      退出      |

  ```bash
  ----------------------
  ls -a # 显示隐藏文件和隐藏目录
  ls -h # 文件大小单位显示，默认是字节
  ls -l # 以列表方式显示
  /home > haha.txt # 会将/home目录下面的文件名覆盖写入haha.txt中
  /test >> hehe.txt # 会将/test目录下的文件名追加到hehe.txt末尾
  cat 1.txt 2.txt > 3.txt # 将两个文件内容写入3.txt中并展示
  more 文件 # 查看内容 (和man命令操作一样)
  uname -a # 详细输出所有信息，依次为内核名称，主机名，内核版本号，内核版本，硬件名，处理器类型，硬件平台类型，操作系统名称
  uname -v # 显示显示操作系统是第几个 version 版本
  ps aux | grep helloworld # 查看所有helloworld进程
  ```

  

- #### yum

  - ```bash
    yum [options] [command][package...]
    # option: -h(帮助) -y(当安装过程提示选择全为yes) -q(不显示安装过程)
    yum update # 更新所有软件
    yum install [package名称] # 安装指定软件
    yum update [package名称] # 更新指定的软件
    yum remove [package名称] # 删除指定软件
    ```

  - 

- #### 文件解压缩操作

  - ```bash
    tar zxvf  文件名.tgz  -C # 文件解压目录
    ```

- #### ssh相关操作

  - ```bash
    ssh @root ip地址 # 
    scp 目标ip地址:/目标文件夹下的文件(文件路径) 本地文件路径 # 将远端文件拉到本地
    ```

- #### docker

  - ```bash
    sudo service docker start # 启动docker
    sudo service docker restart # 重启docker
    sudo service docker stop # 停止docker
    ```

  - ```bash
    sudo docker rmi 镜像id或镜像名 # 删除镜像
    sudo docker image ls # 查看镜像
    sudo docker load -i 镜像路径或者备份镜像路径 # 镜像解压
    ```

  - ```bash
    sudo docker container ls # 查看正在运行的容器
    sudo docker container ls -a # 查看所有的容器
    sudo docker ps -a # 查看所有容器
    ----------------------------------------------
    sudo docker run [option] 镜像名 [向启动容器中传入的命令]
    	常用可选参数说明：
    * -i 表示以《交互模式》运行容器。
    * -t 表示容器启动后会进入其命令行。加入这两个参数后，容器创建就能登录进去。即分配一个伪终端。
    * --name 为创建的容器命名。
    * -v 表示目录映射关系，即宿主机目录:容器中目录。注意:最好做目录映射，在宿主机上做修改，然后共享到容器上。 
    * -d 会创建一个守护式容器在后台运行(这样创建容器后不会自动登录容器)。 
    * -p 表示端口映射，即宿主机端口:容器中端口。
    * --network=host 表示将主机的网络环境映射到容器中，使容器的网络与主机相同。
    ------------------------------------------------
    sudo docker run -dit --name=haha hehe # 开启守护式容器hehe,重命名为haha
    sudo docker exec -it 容器名或容器id  进入后执行的第一个命令 # 进入到容器内部交互环境
    sudo docker container stop 容器名或容器id # 停止容器
    sudo docker container kill 容器名或容器id # kill容器
    sudo docekr container start 容器名或容器id # 启动容器
    sudo docker container rm 容器名或容器id # 删除容器(正在运行的容器无法删除)
    sudo docker commit 容器名 镜像名 # 将容器制作成镜像
    sudo docker save -o 保存的文件名 镜像名 # 将镜像打包备份
    ```

- #### 网卡操作

- #### 用户操作

  - ```bash
    usermod 
    ```

  - 

