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

### 规范约束集
TODO

### 接口模板集
TODO

### 字段模板集
TODO

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

####规范集
![](http://gtms04.alicdn.com/tps/i4/TB1mRdsGXXXXXaOXFXXm3AGHXXX-990-800.png)

####模板集
![](http://gtms03.alicdn.com/tps/i3/TB1JARtGXXXXXapXXXXm3AGHXXX-990-800.png)