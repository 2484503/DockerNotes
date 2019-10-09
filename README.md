# Docker笔记
****

**docker pull mysql之后，设置密码，端口等命令：**

    docker run -v /D/MySqlData:/var/lib/mysql -e TZ=Asia/Shanghai -e MYSQL_ROOT_PASSWORD=123456 -p 33060:3306 -d mysql:5.7 --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci

**docker中 启动所有的容器命令：**

    docker start $(docker ps -a | awk '{ print $1}' | tail -n +2)

**docker中 关闭所有的容器命令：**

    docker stop $(docker ps -a | awk '{ print $1}' | tail -n +2)
    
**docker中 删除所有的容器命令：**

    docker rm $(docker ps -a | awk '{ print $1}' | tail -n +2)

**docker中 删除所有的镜像：**

    docker rmi $(docker images | awk '{print $3}' |tail -n +2)

