---
title: swan.sendSocketMessage
header: develop
nav: api
sidebar: websocket_swan-sendSocketMessage
---

 

**解释**：通过 WebSocket 连接发送数据，需要先调用 swan.connectSocket，并在 swan.onSocketOpen 回调之后才能发送。

**百度APP中扫码体验：**

<img src="https://b.bdstatic.com/miniapp/assets/images/doc_demo/sendSocketMessage.png"  class="demo-qrcode-image" />

**方法参数**：Object object

**`object`参数说明**：

|属性名 |类型  |必填 | 默认值 |说明|
|---- | ---- | ---- | ----|----|
|data| String | 是 | | 需要发送的内容|
|success   |Function  |  否  | |接口调用成功的回调函数 |
|fail  |Function  |  否 | | 接口调用失败的回调函数|
|complete   | Function   | 否 | |  接口调用结束的回调函数（调用成功、失败都会执行）|

**图片示例**：

<div class="m-doc-custom-examples">
    <div class="m-doc-custom-examples-correct">
        <img src=" https://b.bdstatic.com/miniapp/images/sendSocketMessage.gif">
    </div>
    <div class="m-doc-custom-examples-correct">
        <img src=" ">
    </div>
    <div class="m-doc-custom-examples-correct">
        <img src=" ">
    </div>     
</div>

**代码示例**：

<a href="swanide://fragment/a1272c3dcff4f89bc4081d4a8c590d4c1572997122605" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>

* 在 js 文件中

```js
Page({
    sendSocketMessage() { 
        swan.onSocketOpen(function () {
            swan.sendSocketMessage({
                data: 'baidu',
                success: res => {
                    swan.showToast({
                        title: 'WebSocket发送数据成功',
                        icon: "none"
                    });
                    console.log('WebSocket发送数据成功', res);
                },
                fail: err => {
                    console.log('WebSocket发送数据失败', err);
                }
            });
        });

        swan.connectSocket({
            url: 'wss://echo.websocket.org',
            header: {},
            success: res => {
                console.log('connectSocket success', res);
            },
            fail: err => {
                console.log('connectSocket fail', err);
            }
        });
    }
});

```

#### 错误码

* Andriod 
 
|错误码|说明|
|--|--|
|302|找不到调起协议对应端能力方法|
|202|解析失败，请检查参数是否正确 |
|1001|执行失败|

* iOS 

|错误码|说明|
|--|--|
|4|参数有误 |
