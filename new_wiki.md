新同学入职工作指南
==================

阅读此文档，你将了解到：
- 新入职需要阅读的文档与注意事项
- 环境安装
- 常用的工具
- 常用的网站
- 工作流程
- F&A

----------------------------

新入职需要阅读的文档
----------------------
[入职文档1](http://wiki.baidu.com/pages/viewpage.action?pageId=487736453)
[入职文档2](http://wiki.baidu.com/pages/viewpage.action?pageId=487736453)
[入职wiki](http://wiki.baidu.com/pages/viewpage.action?pageId=479986941)

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

F&A
-----------
