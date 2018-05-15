新同学入职工作指南
==================

阅读此文档，你将了解到：
- 新入职需要阅读的文档与注意事项
- 环境安装
- 常用的工具
- 常用的网站
- 工作流程
- PHP知识树
- Q&A

----------------------------

新入职需要阅读的文档
----------------------
- [入职文档1](http://wiki.baidu.com/pages/viewpage.action?pageId=487736453)
- [入职文档2](http://wiki.baidu.com/pages/viewpage.action?pageId=487736453)
- [入职wiki](http://wiki.baidu.com/pages/viewpage.action?pageId=479986941)

环境安装
-----------
### phpStorm

常用的工具
-----------
### 服务器的登录与使用(Relay)
#### 功能介绍
公司内部访问所有服务器（开发机、测试机、线上机器等）时，不能直接连接服务器，必须通过relay服务器中转，即需先登陆到一台relay服务器，再连接至需访问的服务器。
#### 登录步骤
1. 去IT部门领取token
2. RSA Token自助服务网址https://rsa.baidu.com/
   完成RSA Token的设置，设置好RSA Token后记住自己的PIN码

3. 登录跳板机

```shell
ssh yourname@relay01.baidu.com
```
用户名(yourname)：入职时分配，一般和邮箱用户名一致。
密码： “个人 PIN” + “token 密码”

4. 登录服务器

```shell
ssh work@cp01-testing-iknow-real03.cp01.baidu.com
password: BwfyZwy
```

**ps: 服务器上的文件可能会被清理。有需要的话，可以在user目录下创建一个自己名字的文件夹, 来保存临时文件。**


### UDA
[点击这里访问uda](http://bigdata.baidu.com/crm)
#### 功能介绍

### CRM
[点击这里访问CRM](http://bigdata.baidu.com/crm)
#### 功能介绍

常用的网站
-----------
**需要注意的是：所有的内部网络都需要登录度管家才能使用。**
[度管家下载](http://zhunru.baidu.com/#/)

- 百度内网

工作流程
-----------
### 上线流程
#### 小需求
- 针对需求：[pv入口修复](http://newicafe.baidu.com/issue/iknownew-2379/show?from=page)
- 上线模块：server-wap-mobile


```flow
st=>start: START
e=>end
cond1=>condition: 询问QA是否需要测试？
op1=>operation: 测试
op2=>operation: 访问[agile](http://agile.baidu.com/#/dashboard/baidu/iknow/server-wap-mobile)到对应项目
op3=>operation: 切换到BranchPipeline,选择对应的分支按步操作到发布。
op4=>operation: 访问[上线管理](http://orp.baidu.com/user/UserProduct/)选择对应产品线
op5=>operation: 选择【上线变更】-- 【发起上线】，填写上线单名称，命名规则："需求说明_cr:xxx_qa:xxx",提交
op6=>operation: 进入到上线单页，按步进行上线操作。点击准备阶段的上线
op7=>operation: 点击预览机上线，上线完毕，查看线上wap页中需求是否已上线
op8=>operation: 点击单台，查看机器名，通过relay登录该台机器，查看日志： log/hhvm/hhvm_error.log  log/mobile/mobile.log.wf

st->cond1
cond1(yes)->op1->op2
cond1(no)->op2
op2->op3->op4->op5->op6->op7->op8->e
```

ps: 预览上线完时，查看线上wap页时，需注意两点：

- url域名改为：http://test.iknow.jx-orp.int.baidu.com/
- 输入脚本：

```javascript
javascript:void function(){
    var d=new Date();
    document.cookie.indexOf('FIS_WAP_DEBUG=YlwtSmt')===-1?d.setFullYear(d.getFullYear()+1):d.setFullYear(d.getFullYear()-1);
    document.cookie='FIS_WAP_DEBUG=YlwtSmt;
    path=/;
    expires='+d.toGMTString()+'';
    document.cookie='DEBUG_WAP_SINGLE_MACHINE=1;
    path=/;
    expires='+d.toGMTString()+'';
    location.reload()}();
```

PHP知识树
-----------
### 代码规范
参见[php代码规范](http://styleguide.baidu.com/style/php/index.html)

Q&A
-----------
