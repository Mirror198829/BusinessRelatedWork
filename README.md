# docker
## 什么是docker?
* Docker的思想来自于集装箱，现在都流行云计算了，云计算就好比大货轮。docker就是集装箱。
* docker是容器，盛放应用和环境

## 概念
* **镜像**（Image）：你暂时可以认为这个就像我们要给电脑装系统用的系统CD盘，里面有操作系统的程序，并且还有一些CD盘在系统的基础上安装了必要的软件，做成的一张 “只读” 的CD。 
* **仓库**（Docker Container）：镜像的仓库，就像git的仓库一样，用来管理Docker镜像的，提供了Docker镜像的上传、下载和浏览等功能，并且提供安全的账号管理可以管理只有自己可见的私人image。就像git的仓库一样，docker也提供了官方的Registry，叫做Dock Hub(http://hub.Docker.com)。**存放镜像的地方。**
* **容器**（Docker Registry）： 俗称Docker的容器，这个是最关键的东西了。Docker Container是真正跑项目程序、消耗机器资源、提供服务的地方，Docker Container通过Docker Images启动，在Docker Images的基础上运行你需要的代码。 容器提供了系统硬件环境，然后使用了Docker Images这些制作好的系统盘，再加上你的项目代码，跑起来就可以提供服务了。**提供镜像运行的环境。**
# Etcd

# Flannel
## 概念
* 针对Kubernetes设计的一个网络规划服务，简单来说，它的功能是让集群中的不同节点主机创建的Docker容器都具有全集群唯一的虚拟IP地址。
* 其模型为全部容器使用一个network，然后在每个host上从network中划分一个子网subnet
* 用于不同主机的Docker server镜像互相访问
* 预先生成网络配置放入Etcd中
## flannel与docker结合
_flannel为docker提供网络服务。flannel服务要优先于docker服务启动_
### flannel服务启动
1. 从etcd中获取network的配置信息
2. 划分subnet，并在etcd中进行注册
3. 将子网信息记录到 `/run/flannel/subnet.env`
4. 之后将会有一个脚本将subnet.env转写成一个docker的环境变量文件`/run/flannel/docker`
### docker服务启动
docker daemon启动，使用 `/run/flannel/subnet.env`中的变量，作为启动参数
### 容器启动
容器之后的启动，就是由docker daemon负责了。因为配置了bip，因此创建出来的容器会使用该网段的ip，并赋给容器。即容器其实还是按照bridge的模式，进行创建的

## Kubernets
