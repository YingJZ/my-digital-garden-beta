---
{"dg-publish":true,"permalink":"//docker/docker/","pinned":true}
---


**镜像 (image)**：和虚拟机模板类似，是容器的模板；虚拟机模板等价于未运行的虚拟机，所以 image 等价于未运行的容器｜可以看作 `class`

**容器 (container)**：

**启动容器**：`docker run [OPTIONS] IMAGE [COMMAND] [ARG...]`
- `OPTIONS`：可选参数，用于配置容器的各种选项，例如端口映射、容器名称等。
- `IMAGE`：必需参数，指定要使用的容器镜像。
- `COMMAND`：可选参数，指定容器启动后要执行的命令。
- `ARG...`：可选参数，传递给容器启动命令的参数。

---

在要打包的应用的目录下，运行 `docker init` 指令，会有一个交互式的引导界面帮助我们创建：
- `.dockerignore`
- `Dockerfile` 一个文本文件，包含了构建【单个】Docker镜像的指令
- `compose.yaml` 一个用于定义和运行【多容器】Docker应用程序的工具

如何运行这个应用？

```shell
docker compose up --build  # 开始前台运行（可用ctrl+C退出）  
docker compose up --build -d  # 开始后台运行  
docker compose down  # 停止运行
```

|特性|Dockerfile|[[工程向/Docker/compose.yaml\|compose.yaml]]|
|---|---|---|
|作用|定义如何构建镜像|定义如何运行容器|
|指令|从基础镜像开始、添加文件、运行命令、设置环境变量等|容器的镜像、端口映射、环境变量、卷挂载等|
|使用|通过`docker build`命令构建镜像|通过`docker-compose up`命令启动和停止容器|