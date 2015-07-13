<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [RAP介绍 & 视频教程](#rap%E4%BB%8B%E7%BB%8D-&-%E8%A7%86%E9%A2%91%E6%95%99%E7%A8%8B)
- [创建文档](#%E5%88%9B%E5%BB%BA%E6%96%87%E6%A1%A3)
  - [登录 & 注册](#%E7%99%BB%E5%BD%95-&-%E6%B3%A8%E5%86%8C)
  - [创建项目](#%E5%88%9B%E5%BB%BA%E9%A1%B9%E7%9B%AE)
  - [管理项目组织](#%E7%AE%A1%E7%90%86%E9%A1%B9%E7%9B%AE%E7%BB%84%E7%BB%87)
- [文档编辑](#%E6%96%87%E6%A1%A3%E7%BC%96%E8%BE%91)
  - [工作区概念](#%E5%B7%A5%E4%BD%9C%E5%8C%BA%E6%A6%82%E5%BF%B5)
  - [接口文档的结构](#%E6%8E%A5%E5%8F%A3%E6%96%87%E6%A1%A3%E7%9A%84%E7%BB%93%E6%9E%84)
  - [保存文档](#%E4%BF%9D%E5%AD%98%E6%96%87%E6%A1%A3)
- [前端Mock工具](#%E5%89%8D%E7%AB%AFmock%E5%B7%A5%E5%85%B7)
  - [引入插件](#%E5%BC%95%E5%85%A5%E6%8F%92%E4%BB%B6)
  - [Mock规则](#mock%E8%A7%84%E5%88%99)
  - [Mock标签的使用](#mock%E6%A0%87%E7%AD%BE%E7%9A%84%E4%BD%BF%E7%94%A8)
    - [显示与隐藏](#%E6%98%BE%E7%A4%BA%E4%B8%8E%E9%9A%90%E8%97%8F)
    - [书写规则](#%E4%B9%A6%E5%86%99%E8%A7%84%E5%88%99)
    - [转义](#%E8%BD%AC%E4%B9%89)
    - [根据请求参数来动态生成MockJS模板](#%E6%A0%B9%E6%8D%AE%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0%E6%9D%A5%E5%8A%A8%E6%80%81%E7%94%9F%E6%88%90mockjs%E6%A8%A1%E6%9D%BF)
  - [Mock插件](#mock%E6%8F%92%E4%BB%B6)
    - [插件的引入](#%E6%8F%92%E4%BB%B6%E7%9A%84%E5%BC%95%E5%85%A5)
    - [插件提供的JS API](#%E6%8F%92%E4%BB%B6%E6%8F%90%E4%BE%9B%E7%9A%84js-api)
      - [设置黑名单](#%E8%AE%BE%E7%BD%AE%E9%BB%91%E5%90%8D%E5%8D%95)
      - [设置白名单](#%E8%AE%BE%E7%BD%AE%E7%99%BD%E5%90%8D%E5%8D%95)
      - [查看当前模式](#%E6%9F%A5%E7%9C%8B%E5%BD%93%E5%89%8D%E6%A8%A1%E5%BC%8F)
      - [设置当前模式](#%E8%AE%BE%E7%BD%AE%E5%BD%93%E5%89%8D%E6%A8%A1%E5%BC%8F)
  - [NodeJS插件](#nodejs%E6%8F%92%E4%BB%B6)
- [后端接口控制台](#%E5%90%8E%E7%AB%AF%E6%8E%A5%E5%8F%A3%E6%8E%A7%E5%88%B6%E5%8F%B0)
  - [如何进入控制台](#%E5%A6%82%E4%BD%95%E8%BF%9B%E5%85%A5%E6%8E%A7%E5%88%B6%E5%8F%B0)
- [自动化测试](#%E8%87%AA%E5%8A%A8%E5%8C%96%E6%B5%8B%E8%AF%95)
- [RAP 快捷键](#rap-%E5%BF%AB%E6%8D%B7%E9%94%AE)
- [接口文档编辑进阶](#%E6%8E%A5%E5%8F%A3%E6%96%87%E6%A1%A3%E7%BC%96%E8%BE%91%E8%BF%9B%E9%98%B6)
  - [接口文档请求链接语法](#%E6%8E%A5%E5%8F%A3%E6%96%87%E6%A1%A3%E8%AF%B7%E6%B1%82%E9%93%BE%E6%8E%A5%E8%AF%AD%E6%B3%95)
    - [自定义JSONP的callback函数名](#%E8%87%AA%E5%AE%9A%E4%B9%89jsonp%E7%9A%84callback%E5%87%BD%E6%95%B0%E5%90%8D)
    - [RESTFul API根据实际传参值决定所匹配接口](#restful-api%E6%A0%B9%E6%8D%AE%E5%AE%9E%E9%99%85%E4%BC%A0%E5%8F%82%E5%80%BC%E5%86%B3%E5%AE%9A%E6%89%80%E5%8C%B9%E9%85%8D%E6%8E%A5%E5%8F%A3)
  - [最外层为数组的接口](#%E6%9C%80%E5%A4%96%E5%B1%82%E4%B8%BA%E6%95%B0%E7%BB%84%E7%9A%84%E6%8E%A5%E5%8F%A3)
    - [指令集(@deprecated)](#%E6%8C%87%E4%BB%A4%E9%9B%86@deprecated)
    - [表单选项](#%E8%A1%A8%E5%8D%95%E9%80%89%E9%A1%B9)
  - [RESTful API的支持](#restful-api%E7%9A%84%E6%94%AF%E6%8C%81)
    - [参数化的请求路径](#%E5%8F%82%E6%95%B0%E5%8C%96%E7%9A%84%E8%AF%B7%E6%B1%82%E8%B7%AF%E5%BE%84)
    - [根据实际传参值决定所匹配接口](#%E6%A0%B9%E6%8D%AE%E5%AE%9E%E9%99%85%E4%BC%A0%E5%8F%82%E5%80%BC%E5%86%B3%E5%AE%9A%E6%89%80%E5%8C%B9%E9%85%8D%E6%8E%A5%E5%8F%A3)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<!-- toc -->
<!-- toc stop -->



## RAP介绍 & 视频教程

<iframe height=498 width=610 src="http://player.youku.com/embed/XNjk5NjMxODA4" frameborder=0 allowfullscreen></iframe>

## 创建文档

### 登录 & 注册

目前只支持 `域帐号登录`，域帐号登录后会自动完成新用户注册及登录流程。

后续我们会补充其它帐号的登录方式（例如：RAP注册用户、微博账号、QQ账号等）

### 创建项目

方法一、在我的主页中，点击+快速创建项目

方法二、点击最上方菜单中的切换团队，通过选择团队->业务线的方式去创建项目

### 管理项目组织

一、首先点击上方菜单中的 `团队切换`，选择自己的团队或子公司。这些是由系统管理员预设的。

二、 选择合适的 `业务线`，您也可以在这里管理业务线。

三、进入业务线后，可在合适的 `分组` 下创建自己的项目。您也可以在这里管理自己的分组。

## 文档编辑

### 工作区概念

完成项目创建后，点击项目链接进入`接口文档工作区`。

工作区分为以下两种模式：

`查看模式（默认）`：查看模式下，会隐藏编辑UI使界面更方便查看，需要进行改动时只需点击右上角的启用编辑按钮，进入编辑模式。

`编辑模式`：编辑模式下，可根据界面提示完成接口文档的编辑工作。

**首次进入项目系统会自动为您创建默认的第一个模块、页面和请求，请根据需求进行修改。**

### 接口文档的结构

- `模块 (Module)` 对应工作区不同的Tab，用户可根据喜好进行设置。往往在大项目或接口较多的项目中使用频繁。比如可自己分账户模块、宝贝模块等等...
- `页面 (Page)` 每个模块下有0至多个页面，RAP中的“页面”是逻辑页面，比如单页应用每一个View都可以算做一个页面，具体如何使用用户根据自己喜好设定即可。
- `请求 (Action)` 每个页面下有0至多个请求，RAP中的“请求”是接口文档最小单位，描述了一个WEB请求中的全部信息。
- `参数 (Parameter)` 每个请求中有请求参数列表和响应参数列表，参数是可以嵌套参数的，用以描述复杂的Object嵌套结构。


### 保存文档

- `保存` 完成编辑后，可通过 `快捷保存` 直接完成保存，也可以通过普通的 `保存` 提交一些有用的注释信息。

- `版本控制` RAP的接口文档不同版本之间可以查看和永久切换。

- `接口文档导出` 您也能通过 `导出文档` 功能将接口文档以Word文件方式导出（Mac下请修改后缀名为html）。

## 前端Mock工具

### 引入插件

RAP会通过分析接口文档自动生成Mock服务，生成动态的模拟数据。您只需引入一行插件代码即可轻松实现RAP Mock的无缝衔接。详见Mock插件部分。

通常情况下，引入顺序为: `KISSY/jQuery库` => `RAP插件`

在使用Magix等附加框架时，请注意引入顺序为：`KISSY/jQuery库` => `RAP插件` => `Magix`

为保证RAP插件正确拦截到基础库，请确保RAP插件紧挨着KISSY/jQuery库加载到页面中。

### Mock规则

默认，RAP会为不同数据类型生成默认的数据，您也可以通过手动编写标签实现更好的Mock行为控制。例如字段 id 需要自增，您可以使用MockJS语法:

```bash
变量名     备注
id|+1     @mock=100

// 表示id从100开始，每次加1
```

具体Mock规则如何填写，请访问<a href="http://mockjs.com" target="_blank">MockJS文档</a>，也可参考RAP平台中MockJS对接的例子。

### Mock标签的使用

#### 显示与隐藏

在编辑Mock规则时，请点击右上角的 `Mock`按钮来显示Mock信息 ，为了接口文档的阅读体验，默认Mock信息会被隐藏。

#### 书写规则

在备注里，Mock标签和普通的备注需要用分号隔开，比如：

某一个参数叫`userId`，备注信息是 `用户ID`, mock标签是 `@mock=123`，则在备注中应该填写:

```bash
用户ID;@mock=123
```

#### 转义

```bash
变量名            备注                   结果
escapeDemo       @mock="123"           "escapeDemo" : "\"123\""
noEscapeDemo     @{mock}="123"       "noEscapeDemo" : ""1,2,3"" // 语法错误
```
默认所有@mock的值会被转义，若不需要转义，请以 **@{mock}** 代替。


#### 根据请求参数来动态生成MockJS模板

通过${page}这样的语法，RAP会根据请求参数的值替换掉${page}对应的位置，page是参数名。例如：

```bash
@mock=${page}
```

表示根据请求参数page来决定mockjs模板，若请求参数page传入的是123，则这里会等价于:@mock=123

如果该模板放置在变量名中，注意变量名是不需要写@mock=的，例如：

```json
{"arr|10" : []}
```

这里表示数组arr的长度是10，如果这里的10需要参数化，则可以这样写：

```
"arr|${total}"
```

则当参数传入total=100时，这里等价于"arr|100"，即生成100个元素。


```bash
@mock=${page=10}
```

表示在请求参数没有page时，默认等价于@mock=10


### Mock插件

#### 插件的引入

RAP提供了 `Mock插件`（暂时仅支持Kissy和jQuery），使用只需要一步。

将以下代码写在KISSY或jQuery js代码之后即可：

```html
<script type="text/javascript" src="http://{{domainName}}/rap.plugin.js?projectId={{projectId}}&mode={{mode}}"></script>
```

其中：

- `{{projectId}}`为用户所编辑的接口在RAP中的项目ID
- `{{mode}}`为RAP路由的工作模式, 默认值为3。

mode不同值的具体含义如下:

- 0 - 不拦截
- 1 - 拦截全部
- 2 - 黑名单中的项不拦截
- 3 - 仅拦截白名单中的项

**白名单会根据RAP中已经编辑的接口文档，自动配置，RAP中未录入的接口不会做拦截**

#### 插件提供的JS API

您也可以通过调用RAP给出的JS API，手动设置黑名单、白名单及查看、设置工作模式

##### 设置黑名单

```bash
RAP.setBlackList(arr);
```

##### 设置白名单

```bash
RAP.setWhiteList(arr);
```

其中arr可以包含匹配字符串，或正则对象，例：['test', /test/g]

##### 查看当前模式

```bash
RAP.getMode();
```

##### 设置当前模式

```bash
RAP.setMode(1);
```
### NodeJS插件

[插件地址](https://www.npmjs.org/package/rap-node-plugin)

具体文档、安装方法请查看该链接。

## 后端接口控制台

### 如何进入控制台

控制台以RAP文档的`页面`为单位，通过下图中标记的ICON可进入控制台。

<img src="http://gtms03.alicdn.com/tps/i3/T1UOo_FAhdXXcFSA6Q-1048-640.png" width="600" />

控制台的主要功能:

1. 自测功能，自动根据参数提供请求参数输入界面，后端方便自测
2. 校验功能，对实际后端输出是否符合接口规范做校验，提示缺少、多余的字段
3. 日志功能，提供日志分析，时间记录等

## 自动化测试

RAP开放了Mock规则的API，QA或对此有需求的同学可以通过RAP API去访问和编辑Mock规则，为自动化测试提供便利。


## RAP 快捷键

- `Alt + F` 工作区搜索，候选列表出现时可通过上、下、回车键操作
- `Ctrl + Enter` 位于参数编辑时，根据当前行的参数标识或参数名称自动补全
- `Tab` 位于参数编辑时，自动切换到下一个位置
- `Shift + Tab` 位于参数编辑时，自动切换到上一个位置

## 接口文档编辑进阶

### 接口文档请求链接语法

#### 自定义JSONP的callback函数名
`[callback]` 表示参数`callback`会用作JSONP的回调key，若实际请求为getItem?callback=foo，则返回结果为:foo({...});
```
http://www.taobao.com/getItem?[callback]=foo
```

#### RESTFul API根据实际传参值决定所匹配接口
RESTFul API经常根据具体参数值决定接口，例如下面两个接口的路径是一样的，只是path传参不同。

默认情况下RAP会根据`相对路径`去匹配接口，为了在匹配接口时考虑参数的`值`，需要在接口的请求链接中，将该参数用{path}标记出来，并赋值，这样MOCK工具在匹配该接口时，会根据参数path的值来匹配到正确的接口。
```
http://www.taobao.com/getREST?{path}=delete  // 删除接口
http://www.taobao.com/getREST?{path}=update  // 更新接口
```



### 最外层为数组的接口

#### 指令集(@deprecated)
需要在接口描述的开头增加一条指令：@type=array_map;@length=1
表示返回的最外层结构是数组，长度是1。

#### 表单选项
在编辑接口详情信息表单时，下方有"返回格式"选项。
但数组长度仍然需通过@length指令控制。

### RESTful API的支持

#### 参数化的请求路径
一些常见的RESTful API，如：www.example.com/data/100/query 请在RAP的请求链接中填写：

```bash
www.example/data/:id/query
```
这里:id会匹配任意的`数字`

对于复杂的情况，如：www.example.com/biz1432/query 可以使用正则写法：

```bash
reg:www.example/biz[0-9]{4}/query
```

这里MOCK服务会根据正则来匹配正确的接口。

具体例子请参见项目：[RESTful API支持](http://{{domainName}}/workspace/myWorkspace.action?projectId=265&mock=true)


#### 根据实际传参值决定所匹配接口
RESTFul API经常根据具体参数值决定接口，例如下面两个接口的路径是一样的，只是path传参不同。

默认情况下RAP会根据`相对路径`去匹配接口，为了在匹配接口时考虑参数的`值`，需要在接口的请求链接中，将该参数用{path}标记出来，并赋值，这样MOCK工具在匹配该接口时，会根据参数path的值来匹配到正确的接口。
```
http://www.taobao.com/getREST?{path}=delete  // 删除接口
http://www.taobao.com/getREST?{path}=update  // 更新接口

## 开放API

### API1：返回RAP项目的模型数据，到接口层级。

#### 路径和请求参数

```javascript
http://{domainName}/api/queryModel.do?projectId={projectId}&ver={ver}
```

- `{projectId}`为项目ID
- `{ver}`为版本号，不传默认返回当前版本
- `{domainName}`RAP的域名，与您访问RAP页面中的域名一致

#### 响应数据结构

返回的对象有3个字段，分别是：

- `model` - 细化到action层级的项目模型信息
- `code` - 错误码，正确返回200
- `msg` - 错误消息，正确返回空字符串

#### EXAMPLE

链接：`http://{domainName}/api/queryModel.do?projectId=423&ver=0.0.0.2`

```json
{"model":{"moduleList":[{"id":518,"pageList":[{"id":738,"interfaceList":[{"id":2024,"desc":"","reqUrl":"a","name":"某请求","reqType":"1"},{"id":2025,"desc":"","reqUrl":"bbb","name":"bbb","reqType":"1"}],"name":"某页面","intro":""}],"name":"某模块（点击编辑后双击修改）","intro":""}],"id":429,"name":"临时项目一会儿删掉不要动","ver":"0.0.0.4","intro":""},"code":200,"msg":""}
```

### API2：返回具体一个接口的JSON Schema接口详情

#### 路径和请求参数

```javascript
http://{domainName}/api/querySchema.do?actionId={actionId}&ver={ver}&projectId={projectId}&type={type}
```

其中

- `{actionId}`为接口的ID
- `{ver}`和`{projectId}`均为可选参数，同时出现表示指定某一版本的接口。
- `{type}`值为request时表示返回请求参数的schema，其它值或不传默认返回响应参数的schema
- `{domainName}`RAP的域名，与您访问RAP页面中的域名一致

#### 响应数据结构

返回的对象有3个字段，分别是：

- `schema` - 接口的JSON SCHEMA(v4标准)
- `code` - 错误码，正确返回200
- `msg` - 错误消息，正确返回空字符串

#### EXAMPLE

链接：`http://{domainName}/api/querySchema.do?projectId=429&actionId=2024&ver=0.0.0.2`

```json
{"schema":{"id":2024,"$schema":"http://json-schema.org/draft-04/schema","properties":{"resParam":{"id":38393,"title":"某响应参数","description":"","format":"MOCKJS||","required":false,"type":"number"},"a":{"id":38392,"title":"","description":"","format":"MOCKJS||","required":false,"type":""}},"required":"false","type":"object"},"code":200,"msg":""}
```
f

#### 路径和参数

```javascript
http://{domainName}/api/queryRAPModel.do?projectId={projectId}
```

其中

- `{projectId}`为项目的ID，在RAP文档URL中可以看到


### API2：返回具体一个接口的JSON Schema接口详情


### API3：获取一整个RAP项目的文档JSON数据（推荐）

#### 链接

```
http://{domainName}/api/queryRAPModel.do?projectId={projectId}
```

#### 参数
* {projectId} 项目ID


### API4：获取白名单

#### 链接

```
http://{domainName}/mock/getWhiteList.do?projectId={projectId}
```

#### 参数

* {projectId} 项目ID

### API5: 校验接口

```
http://{domainName}/mock/validateAPI/{relativePath}
```

#### 参数

* {relativePath} 相对路径，与/mockjs/类似。


## 常见问题

### 如何导入JSON到请求参数

- 1). 给你的数据最外层加一层，比如你现在的数据是{data}，修改为：{"json":{data}}
- 2). 导入到响应参数; 
- 3). 新增一个请求参数，在第一列输入json(也就是同名)后`ctrl + enter`来执行一键复制;4). 删掉响应参数里的json参数。

类似的，如果你不想wrap到一个参数里，一样是导入到响应参数，然后需要copy哪个就输入相同的变量名后`ctrl+enter`复制过去就好。

### 项目路由有什么用？

项目路由帮助多项目之间共享数据。比如项目A想借用项目B的数据，则在项目A的项目路由中添加B的projectId(在URL中可以查看到当前项目ID）

更复杂的例子，项目A的项目路由设置了23,35,38，则：

当请求项目A的MOCK数据时，若在A中找不到，则会去ID为23的项目找，若依然找不到会去ID为35的项目中，一直到ID为38的项目依然找不到则无结果返回。

### 我使用的AngularJS如何使用RAP插件？

感谢@义宇 提供AngularJS版RAP插件：
[https://github.com/goto100/ng-rap](https://github.com/goto100/ng-rap)

### 有办法让RAP服务直接返回MockJS数据，而不是MockJS模板吗？
可以的，只要将请求路径中的/mockjs/修改为/mockjsdata/即可，例如：

```
http://{{domainName}}/mockjs/79/rap_mockjs_rules_demo.do?
```

将返回MockJS模板，而

```
http://{{domainName}}/mockjsdata/79/rap_mockjs_rules_demo.do?
```

会返回MockJS数据。

```
小提示：为什么返回MOCK规则而不是数据？

默认RAP的MOCK服务返回的是Mock.js模板，如果使用RAP插件，插件会负责Mock模板=>Mock数据的转换工作。
这样做的好处：
1. 可以直观看到数据生成的规则
2. 节省传输带宽
3. 更加灵活，提供在特殊场景二次修改规则的机会。
```
