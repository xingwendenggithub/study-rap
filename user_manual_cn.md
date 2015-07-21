# RAP用户手册

`更新时间：2015/7/21`

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [创建RAP文档](#%E5%88%9B%E5%BB%BArap%E6%96%87%E6%A1%A3)
  - [登录、注册](#%E7%99%BB%E5%BD%95%E3%80%81%E6%B3%A8%E5%86%8C)
  - [创建项目](#%E5%88%9B%E5%BB%BA%E9%A1%B9%E7%9B%AE)
  - [管理项目组织](#%E7%AE%A1%E7%90%86%E9%A1%B9%E7%9B%AE%E7%BB%84%E7%BB%87)
- [文档编辑](#%E6%96%87%E6%A1%A3%E7%BC%96%E8%BE%91)
  - [工作区](#%E5%B7%A5%E4%BD%9C%E5%8C%BA)
  - [接口文档的结构](#%E6%8E%A5%E5%8F%A3%E6%96%87%E6%A1%A3%E7%9A%84%E7%BB%93%E6%9E%84)
  - [文档保存](#%E6%96%87%E6%A1%A3%E4%BF%9D%E5%AD%98)
  - [RAP快捷键](#rap%E5%BF%AB%E6%8D%B7%E9%94%AE)
  - [接口文档编辑进阶](#%E6%8E%A5%E5%8F%A3%E6%96%87%E6%A1%A3%E7%BC%96%E8%BE%91%E8%BF%9B%E9%98%B6)
- [前端工具](#%E5%89%8D%E7%AB%AF%E5%B7%A5%E5%85%B7)
  - [前端Mock数据生成](#%E5%89%8D%E7%AB%AFmock%E6%95%B0%E6%8D%AE%E7%94%9F%E6%88%90)
- [后端工具](#%E5%90%8E%E7%AB%AF%E5%B7%A5%E5%85%B7)
  - [后端接口控制台Page Tester](#%E5%90%8E%E7%AB%AF%E6%8E%A5%E5%8F%A3%E6%8E%A7%E5%88%B6%E5%8F%B0page-tester)
- [测试工具](#%E6%B5%8B%E8%AF%95%E5%B7%A5%E5%85%B7)
  - [自动化测试](#%E8%87%AA%E5%8A%A8%E5%8C%96%E6%B5%8B%E8%AF%95)
- [开放API](#%E5%BC%80%E6%94%BEapi)
  - [API1：返回RAP项目的模型数据，到接口层级。](#api1%EF%BC%9A%E8%BF%94%E5%9B%9Erap%E9%A1%B9%E7%9B%AE%E7%9A%84%E6%A8%A1%E5%9E%8B%E6%95%B0%E6%8D%AE%EF%BC%8C%E5%88%B0%E6%8E%A5%E5%8F%A3%E5%B1%82%E7%BA%A7%E3%80%82)
  - [API2：获取JSON格式的RAP接口文档数据](#api2%EF%BC%9A%E8%8E%B7%E5%8F%96json%E6%A0%BC%E5%BC%8F%E7%9A%84rap%E6%8E%A5%E5%8F%A3%E6%96%87%E6%A1%A3%E6%95%B0%E6%8D%AE)
  - [API3：获取项目白名单（所有接口路径列表）](#api3%EF%BC%9A%E8%8E%B7%E5%8F%96%E9%A1%B9%E7%9B%AE%E7%99%BD%E5%90%8D%E5%8D%95%EF%BC%88%E6%89%80%E6%9C%89%E6%8E%A5%E5%8F%A3%E8%B7%AF%E5%BE%84%E5%88%97%E8%A1%A8%EF%BC%89)
  - [API4：校验真实数据的正确性](#api4%EF%BC%9A%E6%A0%A1%E9%AA%8C%E7%9C%9F%E5%AE%9E%E6%95%B0%E6%8D%AE%E7%9A%84%E6%AD%A3%E7%A1%AE%E6%80%A7)
  - [API5: 通过Open API修改Mock规则（接口级）](#api5-%E9%80%9A%E8%BF%87open-api%E4%BF%AE%E6%94%B9mock%E8%A7%84%E5%88%99%EF%BC%88%E6%8E%A5%E5%8F%A3%E7%BA%A7%EF%BC%89)
- [常见问题](#%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)
  - [如何导入JSON到请求参数](#%E5%A6%82%E4%BD%95%E5%AF%BC%E5%85%A5json%E5%88%B0%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0)
  - [项目路由有什么用？](#%E9%A1%B9%E7%9B%AE%E8%B7%AF%E7%94%B1%E6%9C%89%E4%BB%80%E4%B9%88%E7%94%A8%EF%BC%9F)
  - [我使用的AngularJS如何使用RAP插件？](#%E6%88%91%E4%BD%BF%E7%94%A8%E7%9A%84angularjs%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8rap%E6%8F%92%E4%BB%B6%EF%BC%9F)
  - [有办法让RAP服务直接返回MockJS数据，而不是MockJS模板吗？](#%E6%9C%89%E5%8A%9E%E6%B3%95%E8%AE%A9rap%E6%9C%8D%E5%8A%A1%E7%9B%B4%E6%8E%A5%E8%BF%94%E5%9B%9Emockjs%E6%95%B0%E6%8D%AE%EF%BC%8C%E8%80%8C%E4%B8%8D%E6%98%AFmockjs%E6%A8%A1%E6%9D%BF%E5%90%97%EF%BC%9F)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<!-- toc -->
<!-- toc stop -->



该文档详细介绍了RAP的使用方法，初学者建议通过[RAP视频学习中心](http://thx.github.io/RAP/study.html) 观看演示视频，帮助更好的上手。若文档不能解决亲的疑问，请在[Issues](https://github.com/thx/RAP/issues)中发帖，也欢迎关注我的新浪微博`@Bosn`。

## 创建RAP文档

### 登录、注册

对于阿里内网的同学，建议使用域账号登陆。非阿里的同学，请直接通过右上角的注册按提示完成注册和登陆操作即可。

### 创建项目

有两个办法创建项目：

1. 在我的主页点击`+`按钮快速创建新项目
1. 点击上方菜单中的切换团队，通过选择团队 => 业务线的方式定位到合适的分组，在分组下点击`+`创建该分组下的项目

### 管理项目组织

1. 点击上方菜单中 `团队切换`，选择自己的团队或子公司，这些是由系统管理员预设的。
1. 选择合适 `业务线`，您也可以在这里管理（添加、编辑）业务线。
1. 进入业务线后，在合适 `分组` 下创建自己的项目。您也可在这里管理分组。

## 文档编辑

### 工作区

完成项目创建后，点击项目链接进入到`接口文档工作区`。

工作区分为以下两种模式：

1. `查看模式（默认）`：查看模式下，会隐藏编辑用的UI使界面更易于阅读接口文档信息，需要进行改动时只需点击右上角的`编辑`按钮，进入编辑模式。
1. `编辑模式`：编辑模式下，可根据界面提示完成接口文档的编辑工作。具体操作方法见视频教程。

### 接口文档的结构

每个RAP接口文档中的接口，是按照从模块(Tab)、页面、请求的模型去整理的，但这只是系统推荐的整理方式，亲完全可以根据自己的需求来整理，比如把一个页面当做一个模块整理大量的接口也是没问题的。

- `模块 (Module)` 对应工作区不同的Tab，用户可根据喜好进行设置。往往在大项目或接口较多的项目中使用频繁。比如可自己分账户模块、宝贝模块等等...
- `页面 (Page)` 每个模块下有0至多个页面，RAP中的“页面”是逻辑页面，比如单页应用每一个View都可以算做一个页面，具体如何使用用户根据自己喜好设定即可。
- `请求 (Action)` 每个页面下有0至多个请求，RAP中的“请求”是接口文档最小单位，描述了一个WEB请求中的全部信息。
- `参数 (Parameter)` 每个请求中有请求参数列表和响应参数列表，参数是可以嵌套参数的，用以描述复杂的Object嵌套结构。


### 文档保存

- `保存` 完成编辑后，可通过 `闪存` 完成快速保存，也可以通过普通的 `保存` 提交一些有用的注释信息、版本号信息等内容。

- `版本控制` RAP的接口文档不同版本之间可以查看和切换。

- `接口文档导出` 您也能通过 `导出文档` 功能将接口文档以Word文件方式导出（Mac下请修改后缀名为html）。

### RAP快捷键

- `Alt + F` 工作区搜索，候选列表出现时可通过上、下、回车键操作
- `Ctrl + Enter` 位于参数编辑时，根据当前行的参数标识或参数名称自动补全
- `Tab` 位于参数编辑时，自动切换到下一个位置
- `Shift + Tab` 位于参数编辑时，自动切换到上一个位置

### 接口文档编辑进阶

#### 接口文档请求链接语法

##### 自定义JSONP的callback函数名
`[callback]` 表示参数`callback`会用作JSONP的回调key，若实际请求为getItem?callback=foo，则返回结果为:foo({...});
```
http://www.taobao.com/getItem?[callback]=foo
```

##### RESTFul API根据实际传参值决定所匹配接口
RESTFul API经常根据具体参数值决定接口，例如下面两个接口的路径是一样的，只是path传参不同。

默认情况下RAP会根据`相对路径`去匹配接口，为了在匹配接口时考虑参数的`值`，需要在接口的请求链接中，将该参数用{path}标记出来，并赋值，这样MOCK工具在匹配该接口时，会根据参数path的值来匹配到正确的接口。
```
http://www.taobao.com/getREST?{path}=delete  // 删除接口
http://www.taobao.com/getREST?{path}=update  // 更新接口
```

#### 最外层为数组的接口

##### 指令集(@deprecated)
需要在接口描述的开头增加一条指令：@type=array_map;@length=1
表示返回的最外层结构是数组，长度是1。

##### 表单选项
在编辑接口详情信息表单时，下方有"返回格式"选项。
但数组长度仍然需通过@length指令控制。

#### RESTful API的支持

##### 参数化的请求路径
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


##### 根据实际传参值决定所匹配接口

RESTFul API经常根据具体参数值决定接口，例如下面两个接口的路径是一样的，只是path传参不同。

默认情况下RAP会根据`相对路径`去匹配接口，为了在匹配接口时考虑参数的`值`，需要在接口的请求链接中，将该参数用{path}标记出来，并赋值，这样MOCK工具在匹配该接口时，会根据参数path的值来匹配到正确的接口。

```
http://www.taobao.com/getREST?{path}=delete  // 删除接口
http://www.taobao.com/getREST?{path}=update  // 更新接口
```

## 前端工具

### 前端Mock数据生成

前端Mock工具可以分析接口文档的结构，来生成自测用的数据。建议在查看文档前，看一看视频教程里的Mock部分。

#### 引入插件

您只需引入一行插件代码即可轻松实现RAP Mock的无缝衔接。详见Mock插件部分。

通常情况下，引入顺序为: `KISSY/jQuery库` => `RAP插件`

在使用Magix等附加框架时，请注意引入顺序为：`KISSY/jQuery库` => `RAP插件` => `Magix`

为保证RAP插件正确拦截到基础库，请确保RAP插件紧挨着KISSY/jQuery库加载到页面中。

#### Mock.js规则

默认，RAP会为不同数据类型生成默认的数据，您也可以通过手动编写标签实现更好的Mock行为控制。例如字段 id 需要自增，您可以使用MockJS语法:

```bash
变量名     备注
id|+1     @mock=100

// 表示id从100开始，每次加1
```

具体Mock规则如何填写，请访问<a href="http://mockjs.com" target="_blank">MockJS文档</a>，也可参考RAP平台中MockJS对接的例子。

#### Mock规则填写示范

下面为一个较为典型的RAP接口文档中，Mock规则填写的示范，请参考：

##### 接口文档中的Mock规则
![](https://img.alicdn.com/tps/TB16V7iIFXXXXcBXFXXXXXXXXXX.png)

##### 最终生成的Mock数据
![](https://img.alicdn.com/tps/TB1ADwaIFXXXXamaXXXXXXXXXXX.png)

#### Mock标签的使用

##### 显示与隐藏

注意！！！在编辑Mock规则时，请点击右上角的 `Mock`按钮来显示Mock信息 ，为了接口文档的阅读体验，`默认Mock信息会被隐藏`。

##### 书写规则

在备注里，Mock标签和普通的备注需要用分号隔开，比如：

某一个参数叫`userId`，备注信息是 `用户ID`, mock标签是 `@mock=123`，则在备注中应该填写:

```bash
用户ID;@mock=123
```

##### 转义

```bash
变量名            备注                   结果
escapeDemo       @mock="123"           "escapeDemo" : "\"123\""
noEscapeDemo     @{mock}="123"       "noEscapeDemo" : ""1,2,3"" // 语法错误
```
默认所有@mock的值会被转义，若不需要转义，请以 **@{mock}** 代替。


##### 根据请求参数来动态生成MockJS模板

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


#### Mock插件

##### 插件的引入

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

##### 插件提供的JS API

您也可以通过调用RAP给出的JS API，手动设置黑名单、白名单及查看、设置工作模式

###### 设置黑名单

```bash
RAP.setBlackList(arr);
```

###### 设置白名单

```bash
RAP.setWhiteList(arr);
```

其中arr可以包含匹配字符串，或正则对象，例：['test', /test/g]

###### 查看当前模式

```bash
RAP.getMode();
```

###### 设置当前模式

```bash
RAP.setMode(1);
```
#### NodeJS插件

[插件地址](https://www.npmjs.org/package/rap-node-plugin)

具体文档、安装方法请查看该链接。

## 后端工具

### 后端接口控制台Page Tester

后端工具目前还不成熟，大家有好的提议请在Issues中发帖哦！

#### 如何进入控制台

控制台以RAP文档的`页面`为单位，通过下图中标记的ICON可进入控制台。

<img src="http://gtms03.alicdn.com/tps/i3/T1UOo_FAhdXXcFSA6Q-1048-640.png" width="600" />

控制台的主要功能:

1. 自测功能，自动根据参数提供请求参数输入界面，后端方便自测
2. 校验功能，对实际后端输出是否符合接口规范做校验，提示缺少、多余的字段
3. 日志功能，提供日志分析，时间记录等

## 测试工具

### 自动化测试

RAP开放了Mock规则的API，QA或对此有需求的同学可以通过RAP API去访问和编辑Mock规则，为自动化测试提供便利。目前测试工具还不够完善，欢迎大家在Issues中提出自己的想法。


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


### API2：获取JSON格式的RAP接口文档数据

#### 链接

```
http://{domainName}/api/queryRAPModel.do?projectId={projectId}
```

#### 参数
* {projectId} 项目ID


### API3：获取项目白名单（所有接口路径列表）

#### 链接

```
http://{domainName}/mock/getWhiteList.do?projectId={projectId}
```

#### 参数

* {projectId} 项目ID

### API4：校验真实数据的正确性

#### URL
```
http://{domaiName}/validate/{projectId}/{relativePath}?json={jsonToCompare}
```

#### 输入参数
* `{relativePath}`为相对路径，与mock服务类似。例如：
    * `真实后端接口`为：http://xxx/getJson.php，项目ID为334，则
    * `API验证接口`为：http://{domainName}/validate/334/**getJson.php**.
* `{jsonToCompare}`为想要必要的JSON数据，一般为真实数据
* `{projectId}`为项目ID

#### 输出

输出为一个JSON，最外层是对象，包含两个字段：
* `result` 表示校验结果
    * `result.left` 表示左边（RAP文档）所产生的Mock数据和右边比较的差异
    * `result.right` 表示右边（入参JSON字符串）和左边RAP文档比较的差异
    * 这里之所以区分左边右边，是因为在比较时可能真实数据（右边）少了字段，也可能多了字段，所以需要两边数据相互比较一次，并分别记录在left/right字段下。
* `resultStr` 表示校验结果的中文提示字符串

```json
{
    "result": {
        "left": [{
            "type": "LOST",
            "property": "act_price",
            "namespace": "obj"
        },
        {
            "type": "LOST",
            "property": "coupons",
            "namespace": "obj"
        }],
        "right": [{
            "type": "LOST",
            "property": "coupxxons",
            "namespace": "obj"
        },
        {
            "type": "LOST",
            "property": "acxxt_price",
            "namespace": "obj"
        }]
    },
    "resultStr": "参数 obj.act_price 缺失\n参数 obj.coupons 缺失\n参数 obj.coupxxons 未在接口文档中未定义。\n参数 obj.acxxt_price 未在接口文档中未定义。"
}
```

#### EXAMPLE

##### 测试请求URL

这里在请求里把JSON中的两个字段做了修改，加入了几个XX

```
http://localhost:8001/validate/43/x?json={%22coupxxons%22:[],%22acxxt_price%22:189,%22price%22:40873,%22shop_title%22:%22\u6d4b\u8bd5\u5185\u5bb95y9z%22,%22num%22:32644,%22title%22:%22\u6d4b\u8bd5\u5185\u5bb9bpux%22,%22promotions%22:[],%22num_iid%22:%22\u6d4b\u8bd5\u5185\u5bb92k3r%22,%22pic_url%22:%22\u6d4b\u8bd5\u5185\u5bb95iq5%22,%22desc%22:%22\u6d4b\u8bd5\u5185\u5bb9hbq5%22,%22countdown_sec%22:21553,%22nick%22:%22\u6d4b\u8bd5\u5185\u5bb98519%22,%22wap_detail_url%22:%22\u6d4b\u8bd5\u5185\u5bb90197%22,%22outer_id%22:%22\u6d4b\u8bd5\u5185\u5bb92u8n%22,%22detail_url%22:%22\u6d4b\u8bd5\u5185\u5bb9463m%22,%22earnest%22:85535}
```

##### 返回结果

```json
{
    "result": {
        "left": [{
            "type": "LOST",
            "property": "act_price",
            "namespace": "obj"
        },
        {
            "type": "LOST",
            "property": "coupons",
            "namespace": "obj"
        }],
        "right": [{
            "type": "LOST",
            "property": "coupxxons",
            "namespace": "obj"
        },
        {
            "type": "LOST",
            "property": "acxxt_price",
            "namespace": "obj"
        }]
    },
    "resultStr": "参数 obj.act_price 缺失\n参数 obj.coupons 缺失\n参数 obj.coupxxons 未在接口文档中未定义。\n参数 obj.acxxt_price 未在接口文档中未定义。"
}
```

这里返回了校验结果，在result属性中存放校验结果的对象结构，在resultStr存放提供给你们人类看的提示信息。

### API5: 通过Open API修改Mock规则（接口级）

#### 接口设计

为实现该需求，提供以下接口：

* modify接口，用于修改该项目的接口规则
    * 地址：http://{domainName}/api/modifyMockRules.do
    * 输入
        * rules 规则JSON
        * actionId 接口ID
    * 输出（整个是JSON）
        * isOk 是否成功，true或false
        * msg 错误信息
* reset接口，用于重置该项目所有的接口规则
    * 地址：http://{domainName}/api/resetMockRules.do
    * 输入
        * actionId 接口ID
    * 输出（整个是JSON）
        * isOk 是否成功，true或false
        * msg 错误信息

#### 规则语法设计

采用JSON格式。

```javascript
var rules = {
    "requestParameterList" : [{
    	identifier: "customerName", // 不带mock规则的变量名，用于要修改的字段，必填
    	identifierChange: "customerName|1-2", // 修改后，可省略
    	remarkChange: "@mock=123" // 修改后的规则参数，可省略
       parameterList: [{    // 子参数
           identifier: "id",
           // ... 
           // 对象或装有对象的数组，可能无限嵌套下去，通过parameterList连接   
       }]  
    }]，
    "responseParameterList" : []
}
```


#### 由该API设置的规则如何使用
出于以下原因，通过该Open API设置的MOCK规则与常规的规则区分开：

1. 自动化测试会经常modify, reset，不应该影响到版本。
2. 自动化测试不应该干扰开发者自己设置的Mock规则。

因此，用户一般的Mock服务路径为：

```
http://{domainName}/mockjs/{projectId}/{relativePath}
```

而由该API设置的规则，生效后访问的Mock服务路径为：

```
http://{domainName}/mockjsauto/{projectId}/{relativePath}
```

#### 自动化测试接口(/mockjsauto/)加载规则

1. 访问/mockjsauto/服务
2. 匹配到接口后与/mockjs/一样加载接口模型
3. 加载本API设置的规则数据，覆盖原模型
4. 继续走后续的mock数据生成逻辑

#### modify接口EXAMPLE

##### 请求

```
http://{ipAddress}:8001/api/modifyMockRules.do?actionId=624&rules={%22responseParameterList%22:[{%22identifier%22:%22act_price%22,%22remarkChange%22:%22@mock=189%22}]}
```
#### 返回结果

```json
{"isOk":true,"msg":""}
```

#### Mock接口EXAMPLE

##### 请求

```
http://{ipAddress}:8001/mockjsauto/43/x?
```

##### 返回结果

```json
{"price":71441,"desc":"\u6d4b\u8bd5\u5185\u5bb9u250","act_price":189,"countdown_sec":54565,"shop_title":"\u6d4b\u8bd5\u5185\u5bb938qw","outer_id":"\u6d4b\u8bd5\u5185\u5bb9ln6c","promotions":[],"coupons":[],"detail_url":"\u6d4b\u8bd5\u5185\u5bb94w8u","title":"\u6d4b\u8bd5\u5185\u5bb9cevd","num":61425,"pic_url":"\u6d4b\u8bd5\u5185\u5bb9gu94","wap_detail_url":"\u6d4b\u8bd5\u5185\u5bb98f25","num_iid":"\u6d4b\u8bd5\u5185\u5bb9s38q","nick":"\u6d4b\u8bd5\u5185\u5bb9yknj","earnest":84155}
```

## 常见问题

### 如何导入JSON到请求参数

1. 给你的数据最外层加一层，比如你现在的数据是`{data}`，修改为：`{"json":{data}}`
1. 导入到响应参数; 
1. 新增一个请求参数，在第一列输入json(也就是同名)后`ctrl + enter`来执行一键复制;
1. 删掉响应参数里的json参数。

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
