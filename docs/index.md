# MagicRemote 使用文档

## 场景介绍

* MagicRemote是一个开放平台, 开发者可以通过开放平台注册, 接入自己的应用,网站,平台, 然后通过MagicRemote平台远程控制魅动智能产品.

## 接入流程

1. 注册
    * 前往 [https://mg-dash.vtio.cn/](https://mg-dash.vtio.cn/) 进行注册
    * 验证邮箱
2. 创建应用, 设置回调链接
   ![create-app.png](res/create-app.png)
    * 填写您的应用名
    * 填写您的服务器上接受回调的链接, 回调链接说明请参考 `[下一章]` `如何开发您的应用` `步骤3`

3. 接入您的应用

## 如何开发您的应用

* 流程图

![flow.png](res/flow.png)

1. 1
2. 2
3. 3
    * 在每一次MagicRemote App和您的应用进行配对时, 此链接将会接受开放平台的回调
        * 请在您的服务器上以`POST`方式接受表单, 表单key为`data`
        * data包含:
            * `key` 您 