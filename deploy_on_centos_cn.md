##在centos7上部署RAP

```
系统: centos7.1
rap版本:  rap_release_v0.11.3_20150727.war
```

###安装基础软件

```
wget http://repo.mysql.com/yum/mysql-5.6-community/el/7/x86_64/mysql-community-libs-5.6.26-2.el7.x86_64.rpm
rpm -ivh mysql-community-release-el7-5.noarch.rpm
yum install -y mysql-server nginx tomcat unzip 
```

下载war包

```
wget https://raw.githubusercontent.com/thx/RAP/release/release/rap_release_v0.11.3_20150727.war
```

解压至ROOT

```
unzip -x rap_release_v0.11.3_20150727.war -d ROOT

```


###配置数据库

创建数据库及用户

```
create database rap_db default charset utf8 COLLATE utf8_general_ci;
grant all on rap_db.* to 'rap'@'localhost' IDENTIFIED BY 'password';
flush privileges;
```

初始化数据库,输入刚才创建用户的密码

```
mysql -u rap -p rap_db < ROOT/WEB-INF/classes/database/initialize.sql
```



配置应用中数据库连接

```
vi ROOT/WEB-INF/classes/mysql.local.properties
```

修改为刚才创建的数据库用户名及密码

```
jdbc.username=rap
jdbc.password=password

```

###配置tomcat

```
sudo cp -rf ROOT /var/lib/tomcat/webapps
sudo chown -R tomcat. /var/lib/tomcat/webapps/ROOT
```

重启tomcat

```
systemctl restart tomcat
```


###配置nginx

在/etc/nginx/conf.d 中添加如下配置 ```rap.conf```

注意: 将其中的```xxxx```替换为你的本机ip地址或者域名

```
server {
        listen        80;
        server_name   xxxxx;            #本机IP或者域名
        access_log    /var/log/nginx/rap_access.log;
        charset           utf-8;
        autoindex off;

        location /{
            proxy_pass   http://localhost:8080;

            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

        }
}

```

重启nginx

```
systemctl restart nginx
```


###配置防火墙

```
firewall-cmd --permanent --add-service=http
firewall-cmd --reload
```


###访问

访问http://ip地址或者域名

至此 RAP部署完成

###debug

tomcat日志位于: /var/log/tomcat

nginx日志位于:  /var/log/nginx

###已知bug:

rap应用日志无法打印