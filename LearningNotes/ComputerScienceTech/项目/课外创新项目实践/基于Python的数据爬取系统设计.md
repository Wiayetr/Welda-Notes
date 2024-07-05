# 基于Python的数据爬取系统设计
## 1. web页面与HTML

### 1.1 web页面与HTTP

HTTP是一种网络协议，能够在网络设备之间传输HTML。

HTML是纯文本文件，超文本是指使用超链接的文本。这些网络资源是Web文档。

浏览器浏览一个页面，首先发送请求，获取页面的HTML文档，再解析文档中的资源并发送其他请求，获取包括CSS页面样式表、Javascript脚本、图片等资源。最后整合形成完整的Web文档。

### 1.2 HTML网页与网页结构

通过对HTML内容的解析，可以提取网页中包含的文本内容。

### 1.3基于Python Beautiful Soup库的HTML页面解析

一个Python库，可以对HTML库或XML文件中提取结构化数据。

通过这个库可以对信息进行过滤，提取到自己想要的信息。

### 1.4 浏览器开发者工具

`Ctrl + Shift + I`调出浏览器子窗口

包含：

1. 文档检查器：对HTML、CSS等的查看与编辑。
2. Javascript工具：调试JavaScript变量的值或执行语句。
3. Network工具：包含网页载入过程中Web服务器与浏览器的所有HTTP交互信息

## 2.HTTP基础

HTTP请求的内容即为资源，资源可以是任何格式的数据。

- URL：指示Web上资源文件的具体位置，也被称为Web地址。
- URN：在给定的命名空间用名字指向具体的资源。

Request库提供各种与HTTP请求方法对应的方法，通过这些方法可以发送相应的请求报文。其可以实现几乎所有HTML请求可以实现的功能。

## 3. 网络爬虫基础

自动化浏览网络中的信息，需要按照制定的规则进行。

- 通用网络爬虫：从一些种子URL开始爬取，扩充到整个Web。
- 聚焦网络爬虫：选择性爬取与预定好的主题相关页面的网络爬虫。
- 增量式网络爬虫：对已下载网页采取增量式更新爬行，只爬行新产生的或发送变化的网页。
- 深层网络爬虫：爬行那些大部分内容不能通过静态链接获取的、隐藏在搜索表单后的，只有用户提交一些关键词才能获得的Web页面。

## 4. Python网络爬虫框架Scrapy

提供了简洁的框架来组织代码。



## 实验指导：基于Python的HTML页面信息提取

### BeautifulSoup库与页面解析

1. 创建了`exp_venv`虚拟环境，在虚拟环境中进行操作

2. 选用git仓库`exp_pyms_demo`，将红楼梦的html添加到`crawler_test`文件夹中。

3. `pip install beautifulsoup4`导入bs4库

4. 可进行一系列的`beautifulsoup`操作

5. 发现ECS没有正常连接到仓库。

   重新创建了远程连接，把仓库pull下来。

6. 中途想去改善海外镜像下载时导致流水线镜像构建任务缓慢。

   将基础镜像push到阿里云镜像仓库的国内region时，操作被拒绝，原因可能是没有使用docker login。

   `docker login registry.cn-wulanchabu.aliyuncs.com/exp_pyms_demo/exp_pyms_demo`

   输入账号密码以后就成功了。注意账号密码时容器镜像服务中用户的账号密码，不是Linux中的。



## 实验指导：基于Python的URL目标网页数据爬取

### HTTP方法

- GET：用于获取数据
- HEAD：请求一个与GET请求的响应相同的响应，但没有响应体
- POST：用于将实体提交到指定的资源，通常导致在服务器上的状态变化或副作用。
- PUT：请求有效荷载替换目标资源的所有当前表示
- DELETE：删除所有资源

### HTTP头部获取及应用

浏览者开发工具中，`console`标签下，利用`document.cookie`语句获取cookies

点击`Network`标签栏，刷新页面，第一个条目就是获取HTML页面的请求，点击该条目，就可看到请求头，可将请求头转化成Python Request的代码。

