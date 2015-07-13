<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [需求概述](#%E9%9C%80%E6%B1%82%E6%A6%82%E8%BF%B0)
- [进度 & 分工 & 排期](#%E8%BF%9B%E5%BA%A6-&-%E5%88%86%E5%B7%A5-&-%E6%8E%92%E6%9C%9F)
  - [规范约束集](#%E8%A7%84%E8%8C%83%E7%BA%A6%E6%9D%9F%E9%9B%86)
  - [接口模板集](#%E6%8E%A5%E5%8F%A3%E6%A8%A1%E6%9D%BF%E9%9B%86)
  - [字段模板集](#%E5%AD%97%E6%AE%B5%E6%A8%A1%E6%9D%BF%E9%9B%86)
  - [BPA规范接入 @Bosn](#bpa%E8%A7%84%E8%8C%83%E6%8E%A5%E5%85%A5-@bosn)
  - [RAP Open API @Bosn](#rap-open-api-@bosn)
- [需求详细设计](#%E9%9C%80%E6%B1%82%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1)
  - [规范约束集 @Bosn](#%E8%A7%84%E8%8C%83%E7%BA%A6%E6%9D%9F%E9%9B%86-@bosn)
    - [规范约束集管理入口](#%E8%A7%84%E8%8C%83%E7%BA%A6%E6%9D%9F%E9%9B%86%E7%AE%A1%E7%90%86%E5%85%A5%E5%8F%A3)
- [```](#)
- [-             名称              -       操作     -](#--------------%E5%90%8D%E7%A7%B0----------------------%E6%93%8D%E4%BD%9C------)
- [-             错误码            -     修改 删除  -](#--------------%E9%94%99%E8%AF%AF%E7%A0%81------------------%E4%BF%AE%E6%94%B9-%E5%88%A0%E9%99%A4---)
- [-             日期规范          -     修改 删除  -](#--------------%E6%97%A5%E6%9C%9F%E8%A7%84%E8%8C%83----------------%E4%BF%AE%E6%94%B9-%E5%88%A0%E9%99%A4---)
- [-             人民币规范        -     修改 删除  -](#--------------%E4%BA%BA%E6%B0%91%E5%B8%81%E8%A7%84%E8%8C%83--------------%E4%BF%AE%E6%94%B9-%E5%88%A0%E9%99%A4---)
    - [规范约束集管理界面](#%E8%A7%84%E8%8C%83%E7%BA%A6%E6%9D%9F%E9%9B%86%E7%AE%A1%E7%90%86%E7%95%8C%E9%9D%A2)
  - [接口模板集 @重鱼](#%E6%8E%A5%E5%8F%A3%E6%A8%A1%E6%9D%BF%E9%9B%86-@%E9%87%8D%E9%B1%BC)
    - [接口模板集入口](#%E6%8E%A5%E5%8F%A3%E6%A8%A1%E6%9D%BF%E9%9B%86%E5%85%A5%E5%8F%A3)
    - [接口模板集管理页面](#%E6%8E%A5%E5%8F%A3%E6%A8%A1%E6%9D%BF%E9%9B%86%E7%AE%A1%E7%90%86%E9%A1%B5%E9%9D%A2)
    - [项目创造 及 接口创建 流程](#%E9%A1%B9%E7%9B%AE%E5%88%9B%E9%80%A0-%E5%8F%8A-%E6%8E%A5%E5%8F%A3%E5%88%9B%E5%BB%BA-%E6%B5%81%E7%A8%8B)
  - [字段模板集 @重鱼](#%E5%AD%97%E6%AE%B5%E6%A8%A1%E6%9D%BF%E9%9B%86-@%E9%87%8D%E9%B1%BC)
  - [BPA规范接入](#bpa%E8%A7%84%E8%8C%83%E6%8E%A5%E5%85%A5)
  - [RAP Open API](#rap-open-api)
- [技术详细设计](#%E6%8A%80%E6%9C%AF%E8%AF%A6%E7%BB%86%E8%AE%BE%E8%AE%A1)
- [界面&交互设计](#%E7%95%8C%E9%9D%A2&%E4%BA%A4%E4%BA%92%E8%AE%BE%E8%AE%A1)
  - [交互设计](#%E4%BA%A4%E4%BA%92%E8%AE%BE%E8%AE%A1)
    - [首页](#%E9%A6%96%E9%A1%B5)
    - [团队项目](#%E5%9B%A2%E9%98%9F%E9%A1%B9%E7%9B%AE)
    - [模板集](#%E6%A8%A1%E6%9D%BF%E9%9B%86)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


<!-- toc -->

* [需求概述](#需求概述)
* [进度 & 分工 & 排期](#进度-分工-排期)
  * [规范约束集](#规范约束集)
  * [接口模板集](#接口模板集)
  * [字段模板集](#字段模板集)
  * [BPA规范接入 @Bosn](#bpa规范接入-bosn)
  * [RAP Open API @Bosn](#rap-open-api-bosn)
* [需求详细设计](#需求详细设计)
  * [规范约束集 @Bosn](#规范约束集-bosn)
    * [规范约束集管理入口](#规范约束集管理入口)
    * [规范约束集管理界面](#规范约束集管理界面)
  * [接口模板集 @重鱼](#接口模板集-重鱼)
    * [接口模板集入口](#接口模板集入口)
    * [接口模板集管理页面](#接口模板集管理页面)
    * [项目创造 及 接口创建 流程](#项目创造-及-接口创建-流程)
  * [字段模板集 @重鱼](#字段模板集-重鱼)
  * [BPA规范接入](#bpa规范接入)
  * [RAP Open API](#rap-open-api)
* [技术详细设计](#技术详细设计)
* [界面&交互设计](#界面交互设计)
  * [交互设计](#交互设计)
    * [首页](#首页)
    * [团队项目](#团队项目)
    * [模板集](#模板集)

<!-- toc stop -->

感谢国际站BU兄弟们的给力支持，我们即将在团队管理、项目之间的规范 & 模板共享上，作出重大的改进。同时，我们还会通过引入Blueprint API国际规范来将更多优秀的工具引入到RAP中。

截至到该文档撰写时，RAP仅在阿里内网就已服务于`689`位工程师、`252`项目，承载着`1483`个接口定义。

随着用户&需求爆发式的快速增长，下一年度@RAP小组 的工作重心是：开放平台、业务合作、规范&工具互通。我们将以开放合作的心态来让RAP更加完善。欢迎多多提出issue和pull request。

## 需求概述
在RAP v0.11中，我们将实现：
* 规范约束集
    * 可以在团队(跨项目)级别管理规范约束，比如新建规范约束`『错误码』`，该错误码规范约束可以应用在任意字段中，并会影响Mock数据、数据校验，同时也方便了业务规范信息的管理
* 接口模板集
    * 在创建 & 编辑接口时可以选择模板，例如选择模板`{code : 200, data : $ref, msg : ""}`后，接口中的定义会出现在$ref位置，这对统一管理大量共性结构更加方便。
* 字段模板集
    * 类似于接口模板，一些复杂、共性的字段，例如`{xxxBo : {x : 1, y : 2, z : 3}}`也可以使用字段模板统一管理起来。
* BP规范接入
    * [Blueprint API](http://apiblueprint.org)是国外的基于Markdown的接口规范，目前已经有非常多的工具实现了该规范，RAP也将通过实现Blueprint API来打通各个接口管理功能。在v0.11中，我们首先实现RAP Model => Blueprint API的转换器，并引入第一批优秀的Blueprint API兼容的工具来完善RAP的功能。首批实现功能包含：Aglio(在线文档生成）、Dredd（后端持续集成&测试工具）、api-mock（第三方Mock工具）。
* Open API
    * 我们将通过开放API数据来帮助其它需要接口数据的工具，例如我们和天猫IF-TEST合作为其自动化测试工具提供接口数据。本期我们将开放以下API，具体参文档的[开放API](http://thx.github.io/RAP/tutorials/)部分。
        * queryModel.do `获取RAP项目 => 接口级的数据`
        * querySchema.do `获取接口的详细JSON Schema`
        * queryRAPModel.do `获取项目级、带MockJS模板的RAP整个文档模型`
* 其它改进
    * 会包含一些UI界面的交互改进，并提升用户体验，修复已知问题。
    * 增加功能的定制，非必需功能默认不显示，可在配置中心配置显示的UI功能。防止界面过于复杂。

## 进度 & 分工 & 排期
### 规范约束集 
TODO

### 接口模板集 
TODO

### 字段模板集
TODO

### BPA规范接入 @Bosn
- [x] RAP Data => Blueprint API转换器
- [x] RAP.node服务搭建
- [x] Aglio接入
- [ ] api-mock接入 before 2014.10.30
- [ ] Dredd接入 before 2014.11.30

### RAP Open API @Bosn
- [x] queryModel API
- [x] querySchema API
- [x] queryRAPModel API

## 需求详细设计

### 规范约束集 @Bosn
#### 规范约束集管理入口
点击菜单栏中的『切换团队』可以看到团队下面的规范约束集管理列表（在产品线下方，页面结构和产品线类似）

```
-------------------------------------------------
-             名称              -       操作     -
-------------------------------------------------
-             错误码            -     修改 删除  -
-------------------------------------------------
-             日期规范          -     修改 删除  -
-------------------------------------------------
-             人民币规范        -     修改 删除  -
-------------------------------------------------
```

#### 规范约束集管理界面
点击上部分的『错误码』，进入到错误码管理界面。

![](http://gtms04.alicdn.com/tps/i4/TB1mRdsGXXXXXaOXFXXm3AGHXXX-990-800.png)

规范集

### 接口模板集 @重鱼
模板集由两部份组成，#1 模板入口 及 管理页 #2 现有项目及接口流程修改，`接口模板`这一块主要满足`数据结构的重用`及`标准约定`。

#### 接口模板集入口
右侧为新增版快的入口，点击团队模板进入`模板管理`页面。
用户与团队之前可通过BU进行团队绑定，进行管理，以满足日常工作当中跨团队操作的需求。
![](http://gtms02.alicdn.com/tps/i2/TB1iiXtGXXXXXcXXpXX_9cgHXXX-990-565.png)

#### 接口模板集管理页面
左侧为团队模板，为了`通用`及`业务团队`两类，与RAP的接口操作一致。 点击未节点`+增加`进行新增。
因接口模板为一般接口的一种通用提取操作，所以数据结构与接口数据一致，区别在于模板是基于团队的为`标准`及`高复用性接口`，而接口是基于项目和页面的。
![](http://gtms03.alicdn.com/tps/i3/TB1JARtGXXXXXapXXXXm3AGHXXX-990-800.png)

#### 项目创造 及 接口创建 流程
如果引用`接口模板`，第一步是在于项目创建时，基于项目所选择的团队进行相应的模板选择。
![](http://gtms01.alicdn.com/tps/i1/TB1PRBUGXXXXXaxaXXXl3HeFXXX-1024-768.png)

如果有个别接口不适用于项目中所选择的模板可进行去除或更改。
![](http://gtms02.alicdn.com/tps/i2/TB1L7X2GXXXXXXEXFXXl3HeFXXX-1024-768.png)

选择`接口模板`后，接口详情的页面会套用相关的信息。 灰底的为模板中定义的结果，在模板定义中字段新增`引用`类型以套用接口详情中新增的数据。
![](http://gtms03.alicdn.com/tps/i3/TB17SJ_GXXXXXXtXFXXl3HeFXXX-1024-768.png)

### 字段模板集 @重鱼
与`接口模板`满足的需求不同，`字段模板`主要是为了满`足数据的重用`如一些业务上的`领域模型`及`标准数据定义`。
如下图一些业务对象定义的数据模型，在同一业务线的多个项目中都会被复用，针对业务把来务对象进行封装得出的数据模型我们称之来`领域模型`即`Domain model`与`应用模型`即`Application Model`对应。详情可阅读。

![](http://gtms03.alicdn.com/tps/i3/TB1erh.GXXXXXa1XFXXOqQzGVXX-2848-1960.png)

### BPA规范接入
具体参见[ISSUE19](https://github.com/thx/RAP/issues/19)

### RAP Open API
具体参文档的[开放API](http://thx.github.io/RAP/tutorials/)部分

## 技术详细设计

TODO

## 界面&交互设计

### 交互设计

####首页
![](http://gtms02.alicdn.com/tps/i2/TB1iiXtGXXXXXcXXpXX_9cgHXXX-990-565.png)

####团队项目
![](http://gtms01.alicdn.com/tps/i1/TB1LW0yGXXXXXcNXpXXmOcAHXXX-990-735.png)



####模板集
