## 简介
Docker是一个由GO语言写的程序运行的“容器”； 目前云服务的基石是操作系统级别的隔离，在同一台物理服务器上虚拟出多个主机。Docker则实现了一种应用程序级别的隔离； 它改变我们基本的开发、操作单元，由直接操作虚拟主机（VM）,转换到操作程序运行的“容器”上来。
Docker是2013年Docker 是 PaaS提供商 dotCloud 开源的一个基于 LXC 的高级容器引擎，源代码托管在 Github上, 基于go语言并遵从Apache2.0协议开源，是dotCloud公司的绝处逢生之作，目前该公司以Docker为名。
从2013年3月20日，第一个版本的Docker正式发布到 2014年6月Docker 1.0 正式发布，经历了15个月。 虽然发展历程很短，但Docker正在有越来越流行的趋势。

[Docker](https://zh.wikipedia.org/wiki/Docker) 是一个开源的应用容器引擎，让开发者可以打包他们的应用以及依赖包到一个可移植的容器中，然后发布到任何流行的机器上，也可以实现虚拟化。通俗解释Docker是什么，有个著名的隐喻：集装箱。`在集装箱之前，货物运输没有统一的标准方式进行搬运，于是铁路、公路、海洋等各种运输之间，需要大量的人力作为货物中转，效率极低，而且成本很高。集装箱出现之后，世界上绝大多数的货物运输都可以放到这个神奇的箱子里，然后在公路、铁路、海洋等所有运输场景下，这个箱子都可以不用变化形态直接可以承运，而且中间的中转工作，都可以通过大型机械搞定，效率大大提升。`


## 背景

现代软件开发和计算机技术的快速发展造成了大量异构系统的出现，这给应用开发，测试和部署都带来了巨大的复杂度，如何有效的管理这种复杂度同时保持开发和运维的效率是急待解决的问题。 容器化技术在主机时代已经被证明是非常有效的应用隔离技术，可以帮助企业有效的利用计算资源，同时提供很好的敏捷特性。随着Linux在企业级系统中应用的增多，虚拟化的广泛使用和云计算的兴起，Docker这种围绕容器技术构建的工具/生态系统被广泛接受，成为解决异构系统上应用开发和运维问题的最佳选择，同时也为企业构建混合云数据中心提供了更好的选择和可能性。

## 培训目的

希望通过本次培训学习，搞清楚docker后，开发人员，测试人员，运维人员把docker运用到工作上。
## 安装Docker
Docker有两个版本，一个是Docker-CE(社区版),一个是Docker-EE(企业版)，这里安装社区版就够了，
Docker可在windows，mac，centos，ubuntu等平台使用。其它安装方式请参考[官方文档](https://docs.docker.com/install/#supported-platforms)

1. 卸载旧版本
   ```js
   sudo apt-get remove docker docker-engine docker.io
   ```
2. 更新apt包索引：

   ```js
   sudo apt-get update
   ```
3. 安装包允许apt通过https使用存储库
   ```js
   sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
   ```
4. 添加Docker的官方GPG密钥
   ```js
   sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   ```

5. 设置docker稳定版存储库
   ```js
   sudo add-apt-repository \
   &quot;deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable&quot;
   ```
6. 更新一次docker源索引

   ```js
   sudo apt-get update
   ```

7. 安装docker-ce

   ```js
   sudo apt-get install docker-ce
   ```
## Docker 主要组件

* Docker 镜像(Docker images)
* Docker 仓库(Docker registeries)
* Docker 容器(Docker containers)

## 容器(container)
Docker 容器和文件夹很类似，不同的是，容器是可以运行的。一个Docker容器包含了所有的某个应用运行所需要的环境。每一个Docker容器都是从Docker镜像创建的。Docker容器可以运行、开始、停止、移动和删除。每一个 Docker 容器都是独立和安全的应用平台，Docker 容器是Docker的运行部分。

### Docker 常用基本命令

|常用命令|描述|
|---|---|
|[docker build](https://docs.docker.com/engine/reference/commandline/build/) | 从Dockerfile构建镜像 |
|[docker cp](https://docs.docker.com/engine/reference/commandline/cp/) | 在容器和本地文件系统之间复制文件/文件夹 |
|[docker images](https://docs.docker.com/engine/reference/commandline/images/) | 列出本地镜像|
|[docker ps](https://docs.docker.com/engine/reference/commandline/ps/#description) | 列出容器 |
|[docker restart](https://docs.docker.com/engine/reference/commandline/restart/) | 重启一个或多个容器 |
|[docker rm](https://docs.docker.com/engine/reference/commandline/rm/) | 删除一个或多个容器 |
|[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/) | 删除一个或多个镜像 |
|[docker run](https://docs.docker.com/engine/reference/commandline/run/) | 在新容器中运行命令 |
|[docker save](https://docs.docker.com/engine/reference/commandline/save/) | 将一个或多个镜像保存到tar存档 |
|[docker search](https://docs.docker.com/engine/reference/commandline/search/) | 在Docker Hub(仓库)中搜索镜像 |
|[docker start](https://docs.docker.com/engine/reference/commandline/start/) | 启动一个或多个已停止的容器 |
|[docker stop](https://docs.docker.com/engine/reference/commandline/stop/) | 停止一个或多个正在运行的容器 |
|[docker tag](https://docs.docker.com/engine/reference/commandline/tag/) | 设置镜像标签 |
|[docker pull](https://docs.docker.com/engine/reference/commandline/docker/#child-commands) | 从注册表中提取镜像或存储库 |
|[docker load](https://docs.docker.com/engine/reference/commandline/load/) | 导入镜像到docker |
|[docker exec](https://docs.docker.com/engine/reference/commandline/exec/#examples) | 在正在运行的容器中运行命令 |

更多更详细命令说明请查看[官方文档](https://docs.docker.com/engine/reference/commandline/docker/#child-commands)

### 常用命令使用实例及说明

##### docker ps 实例
语法
```js
#          选项
docker ps [OPTIONS]
```
常用OPTIONS说明：

* --all , -a : 显示所有容器（默认显示刚刚运行）
* --quiet , -q : 仅显示数字ID
* --size , -s : 显示总文件大小

列出当前运行的容器
```js
docker ps
```
`列出如下`：
```js
CONTAINER ID        IMAGE                                                          COMMAND                  CREATED             STATUS              PORTS                           NAMES
700dc6a26247        nginx:1.0                                                      &quot;/usr/sbin/nginx&quot;        9 minutes ago       Up 9 minutes        0.0.0.0:8484-&gt;80/tcp            nginx

```
各个选项说明：
* CONTAINER ID：表示容器的ID
* IMAGE：镜像名称及版本(表示该容器使用的是哪个镜像)
* COMMAND：容器启动后执行的命令
* CREATED：容器创建时间
* STATUS：容器状态
* PORTS：容器端口
* NAMES：容器的名称

##### docker images实例

语法
```js
#                选项          镜像名:版本  
docker images [OPTIONS] [REPOSITORY[:TAG]]
```
列出所有镜像
```js
docker images
```
`列出如下`：
```js
REPOSITORY                                                                              TAG                 IMAGE ID            CREATED             SIZE
nginx                                                                                   1.0                 2980b0d17875        3 hours ago         170MB
```
各个选项说明：
* REPOSITORY：表示镜像的仓库源
* TAG：镜像的标签
* IMAGE ID：镜像ID
* CREATED：镜像创建时间
* SIZE：镜像大小

##### docker load 实例
语法
```js
#            选项
docker load [OPTIONS]
```
加载镜像到docker
```js
docker load &lt; /位置/nginx.tar
```
#### docker run 实例
docker run ：创建一个新的容器并运行一个命令

语法
```js
#           选项   镜像名:版本 执行的命令 环境变量
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```
常用OPTIONS说明：

* -d: 后台运行容器，并返回容器ID；

* -i: 以交互模式运行容器，通常与 -t 同时使用；

* -p: 端口映射，格式为：主机(宿主)端口:容器端口

* -t: 为容器重新分配一个伪输入终端，通常与 -i 同时使用；

* --name: 为容器指定一个名称；

* --volume , -v 目录挂载,表示宿主机文件/文件夹挂载到容器内（宿主机文件或目录:容器内文件或目录）

```js
docker run -d -p 8080:80 --name nginx -v /home/conf:/etc/ nginx:1.0
```


更多Docker Run命令请查看[官方文档](https://docs.docker.com/engine/reference/commandline/run/#parent-command)

#### docker exec 实例

语法
```js
#            选项   容器ID或容器名 执行的命令 环境变量
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```
进入容器
```js
docker exec -it nginx bash
```

常用OPTIONS说明：

* -i:以交互模式运行容器，通常与 -t 同时使用
* -t:为容器重新分配一个伪输入终端，通常与 -i 同时使用

##### docker cp 实例

语法
```js
#          选项   容器ID或容器名:容器内路径 宿主机本地文件/文件夹路径
docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH
#          选项   宿主机本地文件/文件夹路径  容器ID或容器名:容器内路径
docker cp [OPTIONS] SRC_PATH| CONTAINER:DEST_PATH
```

将宿主机index.php文件拷贝到容器96f7f14e99ab的/usr目录下
```js
docker cp /home/index.php 96f7f14e99ab:/usr/
```
将容器96f7f14e99ab的/usr目录拷贝到宿主机的/home目录中
```js
docker cp  96f7f14e99ab:/usr /home/
```

##### docker build 实例

语法
```js
#            选项 dockerfile路径 构建内容路径
docker build [OPTIONS] PATH | URL
```
在当前目录的Dockerfile构建镜像，名为`nginx`，版本`1.0`，`点`表示当前，这里使用`点`需要注意，如果使用`点`，默认寻找`Dockerfile`名称的，不带任何后缀
```js
docker build -t nginx:1.0 .
```

使用-f指定Dockerfile文件位置构建镜像
```js
docker build -t nginx:1.0 -f /home/Dockerfile .
```
常用OPTIONS说明：
* -t ： 指定以“name：tag”格式命名
* -f ： 指定Dockerfile路径

##### docker tag 实例

语法
```js
#               源镜像名:版本    更改后的镜像名:版本
docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
```

给镜像添加一个新的标签
```js
docker tag 860c279d2fec zxd/nginx:1.2
```

### 如何使用已有镜像快速启动一个容器（实践）
**1. 需要资源**
* 准备一个本地nginx镜像（已经打包好的镜像,例如镜像名为`nginx.tar`）或者是Docker仓库公开的镜像

**2. 实践步骤**

* 加载镜像到docker中
  ```js
  docker load &lt; /位置/nginx.tar
  ```
* 查看是否镜像加载成功
  如果存在，那么就已经加载进到docker
  ```js
  docker images
  ```
* 通过刚刚加载的镜像，启动一个容器
  语法
  ```js
  #           选项  容器ID或容器名称 执行的命令 环境变量
  docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
  ```

  ```js
  docker run -d -p 8484:80 --name nginx nginx:1.0
  ```
上面`后台启动`(-d表示后台启动)一个名为`nginx`的容器(container)并且映射出的端口是`8484`，它的镜像(image)来源与`nginx:1.0`

此容器开放80端口，但此容器只能通过内部IP进行访问，需要外部可以访问，那么需要做端口映射：
`-p 8484:80` 将内部端口映射到`8484`端口

`执行以上命令后`：
```js
CONTAINER ID        IMAGE                     COMMAND                  CREATED             STATUS              PORTS                                      NAMES
6748f39cf68a        nginx:1.0             &quot;/usr/sbin/init&quot;         About an hour ago   Up About an hour   0.0.0.0:8484-&gt;80/tcp                             nginx
```
ps：`请注意 0.0.0.0 这一串数字,必须有此映射端口,我们才能通过宿主机的IP地址来访问容器的端口`

例如：宿主机的IP地址是`192.168.0.129`,在浏览器上输入`http://192.168.0.129:8484`就可以访问

## 镜像(image)
Docker 镜像是 Docker 容器运行时的只读模板，每一个镜像由一系列的层 (layers) 组成。
当你改变了一个 Docker 镜像，比如升级到某个程序到新的版本，一个新的层会被创建。因此，不用替换整个原先的镜像或者重新建立(在使用虚拟机的时候你可能会这么做)，只是一个新 的层被添加或升级了。现在你不用重新发布整个镜像，只需要升级，层使得分发 Docker 镜像变得简单和快速。可以理解镜像为系统的iso文件。

在构建镜像前，需要先准备Dockerfile文件
### Dockerfile是什么
Dockerfile 是一个文本格式的配置文件，用户可以使用Dockerfile 快速创建自定义的镜像。

### Dockerfile 基本结构

Dockerfile 由一行行命令语句组成，# 开头的注释行。一般而言，Dockerfile 的内容分为四个部分：
* 基础镜像信息
* 维护者信息
* 镜像操作指令
* 容器启动时执行指令。

### [Dockerfile](https://docs.docker.com/engine/reference/builder/#entrypoint) 基本选项

指令不区分大小写。但是，命名约定为全部大写。

|常用选项|说明|
|---|---|
|FROM `&lt;image name&gt; `| 指定基础镜像 |
|MAINTAINER `&lt;author name&gt;`| 设置维护者信息 |
|RUN 《command》 | 在shell或者exec的环境下执行的命令，RUN指令会在新创建的镜像上添加新的层面.|
|ADD 《src》 《destination》 | 复制文件指令。它有两个参数`&lt;source&gt;`和`&lt;destination&gt;`。destination是容器内的路径。source可以是URL或者是启动配置上下文中的一个文件。|
| COPY 《src》 《destination》 | 基本和ADD类似，不过COPY的`&lt;src&gt;`不能为URL |
|CMD [&quot;param1&quot;,&quot;param2&quot;] | 提供了容器默认的执行命令。 Dockerfile只允许使用一次CMD指令。 使用多个CMD会抵消之前所有的指令，只有最后一个指令生效。|
|EXPOSE `&lt;port&gt;` | 指定容器在运行时监听的端口 |
|ENTRYPOINT [&quot;executable&quot;, &quot;param1&quot;,&quot;param2&quot;] | 允许您配置容器，运行执行的可执行文件 |
|VOLUME [&quot;/data&quot;] | 指令创建具有指定名称的安装点，并将其标记为从本机主机或其他容器保存外部安装的卷。|
|ENV `&lt;key&gt;=&lt;value&gt; ...` | 指令将环境变量`&lt;key&gt;`设置为值`&lt;value&gt;`|

VOLUME 与 -v 的区别

* docker run命令的-v标识创建的挂载点只能对创建的容器有效。

* 通过Dockerfile的 VOLUME 指令可以在镜像中创建挂载点，这样只要通过该镜像创建的容器都有了挂载点。

* 通过 VOLUME 指令创建的挂载点，无法指定主机上对应的目录，是自动生成的。

更详细指令说明请查看[官方文档](https://docs.docker.com/engine/reference/builder/#entrypoint)
### Dockerfile 文本内容实例
```js
# 指定基础镜像
FROM ubuntu

# 设置维护者信息
MAINTAINER 

# 更新软件列表及安装nginx
RUN apt-get update &amp;&amp; apt-get install -y nginx
# 配置nginx.conf文件
RUN echo &quot;\ndaemon off;&quot; &gt;&gt; /etc/nginx/nginx.conf

#COPY /home/docker /

# 容器启动时执行指令
CMD [&quot;/usr/sbin/nginx&quot;]
```

### 构建nginx镜像并启动容器（实践）

1. 编写Dockerfile
   ```js
   # 指定基础镜像
   FROM ubuntu

   # 设置维护者信息
   MAINTAINER 

   # 更新软件列表及安装nginx
   RUN apt-get update &amp;&amp; apt-get install -y nginx
   # 配置nginx.conf文件
   RUN echo &quot;\ndaemon off;&quot; &gt;&gt; /etc/nginx/nginx.conf

   #COPY /home/docker /

   #VOLUME [&quot;/test/upload&quot;]
   
   # 容器启动时执行指令
   CMD [&quot;/usr/sbin/nginx&quot;]
   ```

2. 执行构建
   ```js
   docker build -t nginx:1.0 .
   ```
   -t：以“name：tag”格式命名，name表示名称，tag表示标签，`点`表示当前目录

   以上命令表示：构建一个名为nginx，1.0版本的镜像，`点`表示从当前目录找到默认Dockerfile，并从当前目录构建上下文内容

3. 使用已经构建好的镜像启动容器(container)

   ```js
   docker run -d -p 8484:80 --name nginx nginx:1.0
   ```
