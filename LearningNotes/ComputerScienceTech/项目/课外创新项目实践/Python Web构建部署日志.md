# Python Web构建部署日志

> 实验指导——基于阿里云云效Flow的Python Web服务构建与部署



## 1.构建实验环境

### 1.1 准备本地开发环境

#### 1.1.1 本地环境安装Git与Python3

在Ubuntu（WSL2）中安装git, python3, python3-venv。

#### 1.1.2 在本地环境安装Python第三方库

1. 创建目录exp_pyms_demo
2. 创建Python虚拟环境pyms_venv
3. 使用source命令激活虚拟环境
4. 配置`requirements.txt`文件，提供要安装的python库名`sanic`

问题：无法使用`pip`

解决方案：根据提示安装即可。

### 1.2 准备云服务器ECS

1. 购买ECS
2. 通过高校计划免费获取ECS

### 1.3 在ECS安装Docker引擎和Python3

1. 根据Docker官网提示下载docker引擎
2. 随后在ECS安装Python3与虚拟环境

### 1.4 基于ACR配置镜像仓库

访问ACR产品首页，点击管理控制台进入示例列表，创建使用个人示例。

### 1.5 基于Codeup创建代码库

1. 访问Codeup产品首页
2. 新建代码库`exp_pyms_demo`，注意勾选创建`.gitignore`，选择python模板
3. 默认创建Master分支并提供推荐`.gitignore`
4. 配置SSH访问Codeup，保证本地环境与ECS均可进行配置

注：此处需要install `geomview` 以启用`clip`命令，但没有成功在剪切板获得密钥文本，可直接使用阿里云文档的第一步显示SSH密钥，复制粘贴即可。

## 2. 基于ECS直接部署范例服务

### 2.1 获取范例服务包并解压缩

1. 上传文件到ECS：https://help.aliyun.com/zh/ecs/user-guide/upload-files-to-ecs-instances
2. 解压文件，用mv命令修改文件名
3. 后续操作均在`exp_pyms_demo`中进行
4. 查看所需依赖，创建虚拟环境，激活虚拟环境，安装所需依赖
5. 启动python web服务
6. 选择某台能访问ECS IP的设备，使用浏览器访问`<IP>:8000/`

遇到问题：无法访问

解决：安全组添加8000端口



