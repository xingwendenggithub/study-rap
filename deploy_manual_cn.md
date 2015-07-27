<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [准备工作](#%E5%87%86%E5%A4%87%E5%B7%A5%E4%BD%9C)
- [构建项目](#%E6%9E%84%E5%BB%BA%E9%A1%B9%E7%9B%AE)
  - [获取源代码](#%E8%8E%B7%E5%8F%96%E6%BA%90%E4%BB%A3%E7%A0%81)
  - [导入到IDE](#%E5%AF%BC%E5%85%A5%E5%88%B0ide)
  - [初始化数据库](#%E5%88%9D%E5%A7%8B%E5%8C%96%E6%95%B0%E6%8D%AE%E5%BA%93)
  - [配置文件](#%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6)
  - [配置context-root](#%E9%85%8D%E7%BD%AEcontext-root)
- [启动项目](#%E5%90%AF%E5%8A%A8%E9%A1%B9%E7%9B%AE)
- [常见问题](#%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)
  - [如何管理团队](#%E5%A6%82%E4%BD%95%E7%AE%A1%E7%90%86%E5%9B%A2%E9%98%9F)
  - [如何增加管理员](#%E5%A6%82%E4%BD%95%E5%A2%9E%E5%8A%A0%E7%AE%A1%E7%90%86%E5%91%98)
  - [为什么有mysql.local.properties和mysql.remote.properties两个数据库配置文件?](#%E4%B8%BA%E4%BB%80%E4%B9%88%E6%9C%89mysqllocalproperties%E5%92%8Cmysqlremoteproperties%E4%B8%A4%E4%B8%AA%E6%95%B0%E6%8D%AE%E5%BA%93%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6)
  - [如何获取更新？](#%E5%A6%82%E4%BD%95%E8%8E%B7%E5%8F%96%E6%9B%B4%E6%96%B0%EF%BC%9F)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<!-- toc -->

* [准备工作](#准备工作)
* [构建项目](#构建项目)
  * [获取源代码](#获取源代码)
  * [导入到IDE](#导入到ide)
  * [初始化数据库](#初始化数据库)
  * [配置文件](#配置文件)
  * [配置context-root](#配置context-root)
* [启动项目](#启动项目)
* [常见问题](#常见问题)
  * [如何管理团队](#如何管理团队)
  * [如何增加管理员](#如何增加管理员)
  * [为什么有mysql.local.properties和mysql.remote.properties两个数据库配置文件?](#为什么有mysqllocalproperties和mysqlremoteproperties两个数据库配置文件)
  * [如何获取更新？](#如何获取更新)

<!-- toc stop -->


## 准备工作

若想部署RAP服务，有两个办法：

1. 使用war包部署（推荐）部署方法见issues中的Release帖（不用往下看了...）
2. 自己导入到IDE部署，需要配置J2EE开发环境。（继续往下看）


以下是我们想到的您所需的准备工作：

1. Eclipse/MyEclipse/IDEA(推荐)
2. JDK 1.7+
3. MySQL 5.6.12+  // 太老的MySQL运行initialize.sql会报多timestamp错误
4. Tomcat 6.*+
5. Git

## 构建项目

### 获取源代码

```bash
git clone git@github.com:thx/RAP.git
git checkout release
```

确保您正确的切换到release分支，该分支会去掉一些阿里巴巴公司内网才能正常运作的模块。

### 导入到IDE

以MyEclipse为例，在Package Explorer中右键 -> Import -> Existing Projects into Workspace, 将RAP项目导入进来。

### 初始化数据库

执行`src/database/intialize.sql`，该脚本中包含数据库创建、表&结构创建、必要的初始数据创建的全部内容。

注意！该文件在release分支，路径是[https://github.com/thx/RAP/blob/release/src/database/initialize.sql](https://github.com/thx/RAP/blob/release/src/database/initialize.sql)

### 配置文件

请正确配置`src/mysql.local.properties`中的数据库连接地址、用户名和密码。

### 配置context-root

打开项目属性(Properties), 在Properties -> MyEclipse -> Web -> Web Context-root中，将其修改为/ROOT，以确保RAP部署在tomcat/webapps/ROOT中。

如果是Eclipse, Properties -> Web Project Settings -> Context Root 中修改，确保其为ROOT

## 启动项目

完成上述步骤，将RAP配置到Tomcat中启动即可。

剩下的就是跟着[RAP文档中心](http://thx.alibaba-inc.com/RAP)首页的教程一步一步开启RAP之旅啦！

## 常见问题

### 如何管理团队

在tb_corporation中自行管理，默认在初始化后只有一个默认团队。

### 如何增加管理员

在tb\_role\_and\_user中添加一条记录，user_id是管理员的id，role_id是1(超级管理员)或2(管理员)。

### 为什么有mysql.local.properties和mysql.remote.properties两个数据库配置文件?

为了方便开发环境和线上部署环境的切换，在src/application.xml中搜索mysql.local.properties, 修改成remote即可切换到remote模式。

### 如何获取更新？

我们会确保release的分支上是可用的版本。在开发环境中git pull来获取最新的源码更新，每一期更新都会有对应的update.md请关注并按照上面的指示进行升级工作。
