若想部署RAP服务，有两个办法：

1. 使用war包部署`推荐` 
    * 部署方法见issues中的Release帖，较适合只想用RAP不想自己开发定制功能的。（构建项目不用看，从配置服务器环境开始看即可。）
2. 自己导入到IDE部署
    * 需要配置J2EE开发环境。适合想要研究RAP代码，自己开发想要功能的。


## 构建项目 (war包部署不需要)

### 获取源代码

```bash
git clone git@github.com:thx/RAP.git
git checkout release
```

确保您正确的切换到release分支，该分支会去掉一些阿里巴巴公司内网才能正常运作的模块。

### 导入到IDE

以MyEclipse为例，在Package Explorer中右键 -> Import -> Existing Projects into Workspace, 将RAP项目导入进来。

## 配置服务器环境

### 安装基本工具
1. Eclipse/MyEclipse/IDEA(war包部署不需要)
2. JDK 1.7+
3. MySQL 5.6.12+  // 太老的MySQL运行initialize.sql会报多timestamp错误
4. Tomcat 6.*+
5. Git

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

### Admin初始密码是什么？

由于密码进行了二次MD5加密，所以无法直接登录。

建议自行注册账号，并按照上面的方式添加管理员权限即可。或者自行将字符串进行两次MD5转换后，再设置为admin账户的密码。
如果亲使用源代码自行编译，可以通过设置PRIVATE_CONFIG.java中的adminPassword字段（万用密码）来进行登录。
