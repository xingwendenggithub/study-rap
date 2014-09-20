

<!-- toc -->

* [Create your account](#create-your-account)
  * [Login and register](#login-and-register)
  * [Create project](#create-project)
  * [Manage organizations](#manage-organizations)
* [Document Editing](#document-editing)
  * [Workspace](#workspace)
  * [Structure of interface document](#structure-of-interface-document)
  * [Save your work](#save-your-work)
* [Front-End MOCK tool](#front-end-mock-tool)
  * [Import RAP plugin](#import-rap-plugin)
  * [Mock Rules](#mock-rules)
  * [Mock Tags Details](#mock-tags-details)
    * [Show/Hide](#showhide)
    * [MockJS Rules in RAP](#mockjs-rules-in-rap)
    * [Escaptions](#escaptions)
    * [Dynamically generate MockJS template by request parameters.](#dynamically-generate-mockjs-template-by-request-parameters)
  * [Mock plugin](#mock-plugin)
    * [Import the plugin](#import-the-plugin)
    * [RAP Mock Plugin API](#rap-mock-plugin-api)
  * [NodeJS Plugin](#nodejs-plugin)
* [Back-End tools](#back-end-tools)
  * [How to entered?](#how-to-entered)
* [Test in automation](#test-in-automation)
* [RAP Short Cuts](#rap-short-cuts)
* [Document edit advanced skills](#document-edit-advanced-skills)
  * [URL grammer](#url-grammer)
  * [Outer structure control](#outer-structure-control)
  * [RESTful API support](#restful-api-support)
* [Open API](#open-api)
  * [API1：Return RAP project model data. (from project to action)](#api1return-rap-project-model-data-from-project-to-action)
    * [Path and request parameters](#path-and-request-parameters)
    * [Response data structure](#response-data-structure)
    * [EXAMPLE](#example)
  * [API2：return detail data of specified action](#api2return-detail-data-of-specified-action)
    * [Path and request parameters](#path-and-request-parameters)
    * [Response data structure](#response-data-structure)
    * [EXAMPLE](#example)
* [Common issues](#common-issues)
  * [How to share data between different RAP projects?](#how-to-share-data-between-different-rap-projects)
  * [How to use RAP plugin in AngularJS?](#how-to-use-rap-plugin-in-angularjs)
  * [Any way to let MOCK service returns MockJS data, not MockJS rule templates?](#any-way-to-let-mock-service-returns-mockjs-data-not-mockjs-rule-templates)

<!-- toc stop -->


## Create your account

### Login and register

Press `Register` button on the right top corner, fills the form and submit.

### Create project

* Method 1. In `my home` page, click `+` button create new RAP interface document.
* Method 2. Click `Team` in the top menu, create your project under correct `Team` -> `Business Line` -> `Group`

### Manage organizations

1. Click `team` in top menu, choose your team (Set up by RAP server admin)
2. Choose your `Business Line`, you can also create new one.
3. Choose `Group`, you can also create new one.

## Document Editing

### Workspace

After creating project, click project link to enter `Interface Document Workspace`.

This workspace has two mode:

`View Mode（Default）`：Hide UI for editing, make document be simple to read. When you want to edit, press `Edit` button on the right top corner.

`Edit Mode`：Show all UI for editing.

** First time entered, default module/page/actions will be created. Please enjoy change them. **

### Structure of interface document

- `Module` Every module present for a tab of workspace.
- `Page` Every module has multiple pages.
- `Action` Every page has multiple actions which presents for an interface.
- `Parameter` Every action has multiple parameters, for complex object, parameter may have child parameters.

### Save your work

- `Save` After finished editing, press `Quick Save` to submit without comments, or use `Save` button to submit normally.

- `Version Control` RAP supplies method to see or switch between versions.

- `Document Export` Export word document（Please change file extensions to *.html on Mac OS）

## Front-End MOCK tool

### Import RAP plugin

RAP can dynamically generate Mock service by analyzing interface documents. What you need to do is just put one line code into your project. Press `Plugin Code` to obtain plugin script code.

Pay attention to the script orders, please put RAP plugin script after jQuery/AngularJS/etc to ensure RAP plugin can successfully intercept the base libraries.

### Mock Rules

On default, RAP generate default data of parameter definitions, you can also manage Mock rules by adding Mock tags. eg-> you want to add incrementing `id` field, you can use MockJS grammer:

```bash
Variable Name    Remarks
id|+1            @mock=100

// id will start from `100`, step is `1`
```

Want to know more details of MockJS rules, please visit: <a href="http://mockjs.com" target="_blank">MockJS.com</a>.

### Mock Tags Details

#### Show/Hide

By clicking `Mock` button on the right top corner, you can switch Mock tags visibility. When you just want to handle the document structure, hiding Mock data make document simple to read.

#### MockJS Rules in RAP

Write @mock tags in `remark` columns, remarks should be separated with `@mock` tag by character `;`, eg->

There's a parameter called `userId`, remark is `User ID`, mock tag is `@mock=123`, than we can write in this way:

```
Variable Name       Remark
userId              User Id;@mock=123
```

#### Escaptions

```bash
Variable Name    Remark                Result
escapeDemo       @mock="123"           "escapeDemo" : "\"123\""
noEscapeDemo     @{mock}="123"       "noEscapeDemo" : ""1,2,3"" // Grammer error!
```
all @mock value will be escaped on default, if you don't want, please replaced by **@{mock}**.

#### Dynamically generate MockJS template by request parameters.

eg->

```bash
@mock=${page}
```

`${page}` will be replaced by the real request parameter `page`, eg-> if request link is domain.com?page=10, than this is equal to @mock=10.

```bash
@mock=${page=10}
```
This means if no parameter `page` exists in the HTTP request, default value is 10.

### Mock plugin

#### Import the plugin

After jQuery or other libraries, insert:

```html
<script type="text/javascript" src="http://{domain}/rap.plugin.js?projectId={{projectId}}&mode={{mode}}"></script>
```

In code above：

- `{{projectId}}` is project id
- `{{mode}}` is plugin working mode, default is 3.

mode value explanations:

- 0 - no interceptions
- 1 - all requests will be intercepted.
- 2 - intercept all requests except ones existing in black list.
- 3 - (default) intercept all requests existing in white list.

** white list is configured in default, so RAP plugin won't intercept requests not defined in RAP document **

#### RAP Mock Plugin API

You can manually set up black/white list, set working mode dynamically.

##### Set blacklist

```bash
RAP.setBlackList(arr);
```

##### Set whitelist

```bash
RAP.setWhiteList(arr);
```

arrcan contains strings or regular expression objects, eg-> ['test', /test/g]

##### get current mode

```bash
RAP.getMode();
```

##### set mode

```bash
RAP.setMode(1);
```
### NodeJS Plugin

[Link](https://www.npmjs.org/package/rap-node-plugin)

## Back-End tools

### How to entered?

Click little icon after `page` nodes in the left structure tree.

<img src="http://gtms03.alicdn.com/tps/i3/T1UOo_FAhdXXcFSA6Q-1048-640.png" width="600" />

Main functions in control:

1. Real interface self test
2. Real interface data stucture validation
3. Request Loging


## Test in automation

RAP has opened APIs for testers create their own tools & scripts.


## RAP Short Cuts

- `Alt + F` Search
- `Ctrl + Enter` Auto Complete Parameter
- `Tab` Parameter switch
- `Shift + Tab` Parameter switch back forward

## Document edit advanced skills

### URL grammer

http://www.taobao.com/getItem?[callback]=foo

`[callback]` is to say that `callback` will be the JSONP callback key, eg-> `getItem?callback=foo`, mock request result would be: foo({...});

http://www.taobao.com/getREST?{path}=delete

`{path}` means the parameter `path` will be used for action matching, this feature is usually used in RESTful API. eg-> getRest?path=delete, getRest?path=update, than `getRest?path=delete` matches `http://www.taobao.com/getREST?{path}=delete`, but won't match `http://www.taobao.com/getREST?{path}=update`.

### Outer structure control

On default, the JSON structure is always {}, not [{}].
If you want the outer structure is array, add this into action descriptions:
@type=array_map;@length=1

this means you want the outer structure is array and length is 1.

### RESTful API support

For common RESTful APIs, eg->`www.example.com/data/100/query`

Please fill action url with:

```bash
www.example/data/:id/query
```
`:id` here will match any `number`

For scenes more complex, eg-> `www.example.com/biz1432/query`, we can use regular expression:

```bash
reg:www.example/biz[0-9]{4}/query
```

## Open API

### API1：Return RAP project model data. (from project to action)

#### Path and request parameters

```javascript
http://{domain}/queryModel.do?projectId={projectId}&ver={ver}
```

- `{projectId}` project id
- `{ver}` version number，default is the head version.

#### Response data structure

Returned object has 3 fields:

- `model` - Model data
- `code` - error code, return 200 when successful.
- `msg` - error message ,return '' when successful.

#### EXAMPLE

`http://rap.domain.com/api/queryModel.do?projectId=423&ver=0.0.0.2`

```json
{"model":{"moduleList":[{"id":518,"pageList":[{"id":738,"interfaceList":[{"id":2024,"desc":"","reqUrl":"a","name":"某请求","reqType":"1"},{"id":2025,"desc":"","reqUrl":"bbb","name":"bbb","reqType":"1"}],"name":"某页面","intro":""}],"name":"某模块（点击编辑后双击修改）","intro":""}],"id":429,"name":"临时项目一会儿删掉不要动","ver":"0.0.0.4","intro":""},"code":200,"msg":""}
```

### API2：return detail data of specified action

#### Path and request parameters

```javascript
http://{domain}/querySchema.do?actionId={actionId}&ver={ver}&projectId={projectId}&type={type}
```

其中

- `{actionId}` action id
- `{ver}`和`{projectId}` optional, when specified, will returned action data in specified versions.
- `{type}` optional, "request" stands for request parameters schema, other value or null value presents for response parameters schema.

#### Response data structure

Object returned has 3 fields:

- `schema` - JSON SCHEMA(v4)
- `code` - error code
- `msg` - error messages

#### EXAMPLE

`http://rap.domain.com/api/querySchema.do?projectId=429&actionId=2024&ver=0.0.0.2`

```json
{"schema":{"id":2024,"$schema":"http://json-schema.org/draft-04/schema","properties":{"resParam":{"id":38393,"title":"某响应参数","description":"","format":"MOCKJS||","required":false,"type":"number"},"a":{"id":38392,"title":"","description":"","format":"MOCKJS||","required":false,"type":""}},"required":"false","type":"object"},"code":200,"msg":""}
```

## Common issues

### How to share data between different RAP projects?

Use `project router`, click `Config` button on right top corner, input project ids you want to share, click confirm button to finish.

eg-> In current project(id=1), I set up router field is "23, 33, 5".

When someone request MOCK service with projectId=1, if no matched action, MOCK service will search projectId=23, projectId=33, projectId=5 in order. If none of these projects matched actions, return "no matched action" error.

### How to use RAP plugin in AngularJS?

DEMO

```javascript
	app.config(function($httpProvider) {
    var interceptor = {
        request: function(config) {
            var url = config.url;
            var urls = RAP.getWhiteList();
           
            if (urls.indexOf(url) != -1) {
                config.url = 'http://rap.alibaba-inc.com/mockjsdata/257' + url;
            }

            return config;
        }
    };
   
    $httpProvider.interceptors.push(function() {
        return interceptor;
    });
}); 

```

### Any way to let MOCK service returns MockJS data, not MockJS rule templates?

Yes，just replaced `/mockjs/` to `/mockjsdata/` in MOCK service request urls. eg->

```
http://{domain}/mockjs/79/rap_mockjs_rules_demo.do?
```

changed to 

```
http://{domain}/mockjsdata/79/rap_mockjs_rules_demo.do?
```