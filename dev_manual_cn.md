<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [RAP开发手册](#rap%E5%BC%80%E5%8F%91%E6%89%8B%E5%86%8C)
  - [技术摘要](#%E6%8A%80%E6%9C%AF%E6%91%98%E8%A6%81)
    - [技术选型](#%E6%8A%80%E6%9C%AF%E9%80%89%E5%9E%8B)
    - [目录结构](#%E7%9B%AE%E5%BD%95%E7%BB%93%E6%9E%84)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

	未完待续... updated on 8/5/2015

本文档介绍RAP的技术设计，皆在为开源爱好者和RAP开发者提供指导。有问题欢迎在issue列表中开贴讨论。

# RAP开发手册

## 技术摘要

### 技术选型
技术选型上，其实没有太多的考虑抉择。我在最初写RAP时对J2EE开发并不是很熟悉，因为当时团队都在用，所以就用了...

以下为技术架构：

* 前端
	* DOM库:tangram（百度的坑爹DOM库，也不维护了...后续新功能或重构时考虑移除）
	* UI库:ECUI（个人做的，不维护了...后续新功能或重构时考虑移除）
	* 核心的工作区UI、类Excel编辑等，都是用JS纯手写，主要在rap.js文件里。虽然辣个文件灰常长，但是是有简单的模块化拆分的。
* 后端
	* MySQL
	* Struts 没啥好说的
	* Hibernate 管理一些O/R简单的用HQL确实方便，不过复杂的地方也会自己写SQL
	* Spring 管理依赖，没啥好说的

### 目录结构

* .idea IntelliJ IDEA的项目工程文件（IDEA是一个IDE，类似MyEclipse）
* lab 一些实验性的代码
* out 编译后的输出目录
* src 后端源代码
	* com.taobao.rigel.rap 该命名空间下为各个模块
		* account - 账户相关
		* api - OpenAPI相关
		* auto.generate - 自动化生成相关
		* common - 公共内容
		* mock - MOCK工具相关
		* organization - 公司/组织结构管理相关
		* platform - RAP平台相关（首页、帮助页等等）
		* project - RAP项目相关
		* tester - 测试相关
		* workspace - 文档编辑工作区相关
* test 测试、UT相关
* WebContent 前端源代码
	* account - 账户相关模板
	* bcom - 异步请求的回调模板（其实就是HTML片段，而不是整个HTML页面）
	* common - 公共模板
	* demo - 例子模板
	* mock - MOCK工具页面模板
	* org - 组织结构管理页面模板
	* platform - 平台页面模板
	* stat - **静态文件/资源/包**
	* tcom - 模板宏、函数、所有页面模板公用的母版等
	* tester - 后端控制台、测试页面模板
	* unit-tests - RAP系统的单元测试文件
	* workspace - 文档工作区模板文件
* DATABASE_CHANGE.md 近期数据库变化情况文档
* RAP.iml IntelliJ IDEA的项目工程文件
* README.md RAP文档

### 数据库字段解释
请参考[数据库初始化文件](https://github.com/thx/RAP/blob/master/src/database/initialize.sql)中的注释部分，已经补充了字段注释。
