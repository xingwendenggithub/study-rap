

<!-- toc -->

* [Preparations](#preparations)
* [Build Project](#build-project)
  * [Obtain source code](#obtain-source-code)
  * [Import to IDE](#import-to-ide)
  * [Initialize database](#initialize-database)
  * [Little configurations](#little-configurations)
  * [Context-root](#context-root)
* [Start Server](#start-server)
* [Common issues](#common-issues)
  * [How to manage teams(corporations)?](#how-to-manage-teamscorporations)
  * [How to add administrator?](#how-to-add-administrator)
  * [Why `mysql.local.properties` and `mysql.remote.properties` seperated?](#why-mysqllocalproperties-and-mysqlremoteproperties-seperated)
  * [How to obtain update?](#how-to-obtain-update)

<!-- toc stop -->




## Preparations

Before work of RAP deployment, you should get well prepared with things below:

1. Eclipse/MyEclipse
2. JDK 1.7+
3. MySQL 5.6.12+
4. Tomcat 6.*+
5. Git

## Build Project

### Obtain source code

```bash
git clone git@github.com:thx/RAP.git
git checkout release_en
```

Ensure you switched to branch [release_en], we keep this branch always working correctly.

### Import to IDE

eg-> In MyEclipse, right click in `Package Explorer` -> `Import` -> `Existing Projects into Workspace`

Imports RAP into your workspace.

### Initialize database

Execute `src/database/intialize.sql`，this file contains database objects construction, and essential data.

### Little configurations

Please config `src/mysql.local.properties`, contains database's username/password, path/port, etc.

### Context-root

Open project properties(Properties), `Properties` -> `MyEclipse` -> `Web` -> `Web Context-root` changed to /ROOT.

For Eclipse, `Properties` -> `Web Project Settings` -> `Context Root`, changed to `ROOT`

For other IDEs, please ensure RAP is deployed in ROOT

## Start Server

After complete steps above, start tomcat.

What do you need to do is follow the [User Manual](user_manual) to explorer RAP!

## Common issues

### How to manage teams(corporations)?

In database table `tb_corporation`, cause this data rarely changes, you can just write SQL to manage.

### How to add administrator?

add record into the database table `tb\_role\_and\_user` `user_id` is admin's userId，`role_id` 1(super admin), 2(admin)

### Why `mysql.local.properties` and `mysql.remote.properties` seperated?

This is used for environment switch, you can config local database and remote database, when you want to switch, just alter file `src/applicationContext.xml`, search mysql.*.properties than change it.

### How to obtain update?

We'll ensure release_en branch is always correct. Please focus on RAP wiki, when new release_en comes out, try to git pull from release_en branch. Every new release_en will have md file to tell you how to transfer.
