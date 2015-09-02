<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [构建项目 (war包部署不需要)](#%E6%9E%84%E5%BB%BA%E9%A1%B9%E7%9B%AE-war%E5%8C%85%E9%83%A8%E7%BD%B2%E4%B8%8D%E9%9C%80%E8%A6%81)
  - [获取源代码](#%E8%8E%B7%E5%8F%96%E6%BA%90%E4%BB%A3%E7%A0%81)
  - [导入到IDE](#%E5%AF%BC%E5%85%A5%E5%88%B0ide)
- [配置环境](#%E9%85%8D%E7%BD%AE%E7%8E%AF%E5%A2%83)
  - [安装基本工具](#%E5%AE%89%E8%A3%85%E5%9F%BA%E6%9C%AC%E5%B7%A5%E5%85%B7)
  - [初始化数据库](#%E5%88%9D%E5%A7%8B%E5%8C%96%E6%95%B0%E6%8D%AE%E5%BA%93)
  - [配置文件](#%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6)
  - [配置context-root （war包部署不需要）](#%E9%85%8D%E7%BD%AEcontext-root-%EF%BC%88war%E5%8C%85%E9%83%A8%E7%BD%B2%E4%B8%8D%E9%9C%80%E8%A6%81%EF%BC%89)
- [启动项目](#%E5%90%AF%E5%8A%A8%E9%A1%B9%E7%9B%AE)
- [常见问题](#%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)
  - [如何管理团队](#%E5%A6%82%E4%BD%95%E7%AE%A1%E7%90%86%E5%9B%A2%E9%98%9F)
  - [如何增加管理员](#%E5%A6%82%E4%BD%95%E5%A2%9E%E5%8A%A0%E7%AE%A1%E7%90%86%E5%91%98)
  - [为什么有mysql.local.properties和mysql.remote.properties两个数据库配置文件?](#%E4%B8%BA%E4%BB%80%E4%B9%88%E6%9C%89mysqllocalproperties%E5%92%8Cmysqlremoteproperties%E4%B8%A4%E4%B8%AA%E6%95%B0%E6%8D%AE%E5%BA%93%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6)
  - [如何获取更新？](#%E5%A6%82%E4%BD%95%E8%8E%B7%E5%8F%96%E6%9B%B4%E6%96%B0%EF%BC%9F)
  - [Admin初始密码是什么？](#admin%E5%88%9D%E5%A7%8B%E5%AF%86%E7%A0%81%E6%98%AF%E4%BB%80%E4%B9%88%EF%BC%9F)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

部署方式有两种。

1. 使用编译好的war包部署
    * 适合仅想部署RAP服务，不需开发定制功能的同学
2. 使用源码自行编译、开发后部署
    * 需配置J2EE开发环境， 适合想要研究RAP源代码，开发定制功能的同学

## 构建项目 (war包部署不需要)

### 获取源代码

```bash
git clone git@github.com:thx/RAP.git
git checkout release
```

**确保您正确的切换到release分支**，否则会出现少包，因为master分支引用一些不对外公开的内部组件，不提供给外部用户使用。

### 导入到IDE

以MyEclipse为例，在Package Explorer中右键 -> Import -> Existing Projects into Workspace, 将RAP项目导入进来。

根据您IDE的不同，导入项目的方式也有所差异。建议自行检索，如果您根本不懂Java开发，建议跳过这里用编译好的war包部署吧。 d-  .-b|||

## 配置环境

### 安装基本工具

* 仅使用源码自行编译才需要安装的(即，使用war包部署不需要安装)
    * Eclipse/MyEclipse/IDEA
    * Git
* 都需要安装的
    * JDK 1.7+ `若报错，请尽量使用较新版本`
    * MySQL 5.6.12+  `太老的MySQL运行initialize.sql会报多timestamp错误`
    * Tomcat 6.*+

以上工具如何安装自行检索。

### 初始化数据库

执行**release**分支下的SQL脚本： [src/database/intialize.sql](https://github.com/thx/RAP/blob/release/src/database/initialize.sql)，该脚本中包含数据库创建、表&结构创建、必要的初始数据创建的全部内容。

### 配置文件

请正确配置`src/mysql.local.properties`中的数据库连接地址、用户名和密码。

### 配置context-root （war包部署不需要）

将context-root设置为/，即访问RAP时，必须是http://domain.com/  而不能是 http://domain.com/rap/。

设置context-root不同的IDE设置方法不一样，以MyEclipse/Eclipse举例：
* MyEclipse中，打开项目属性(Properties), 在Properties -> MyEclipse -> Web -> Web Context-root中，将其修改为/ROOT，以确保RAP部署在tomcat/webapps/ROOT中。
* 如果是Eclipse, Properties -> Web Project Settings -> Context Root 中修改，确保其为ROOT

## 启动项目

完成上述步骤，将RAP配置到Tomcat中启动即可。

`注意!RAP暂时仅支持在根目录部署，若使用编译好的war包部署，需将war包改名为ROOT.war，以确保RAP部署在webapps/ROOT中！`

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

### Admin初始密码是什么？

由于密码进行了二次MD5加密，所以无法直接登录。

建议自行注册账号，并按照上面的方式添加管理员权限即可。或者自行将字符串进行两次MD5转换后，再设置为admin账户的密码。
如果亲使用源代码自行编译，可以通过设置PRIVATE_CONFIG.java中的adminPassword字段（万用密码）来进行登录。
