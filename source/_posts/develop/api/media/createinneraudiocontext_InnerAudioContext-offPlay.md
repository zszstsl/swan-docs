---
title: InnerAudioContext.offPlay
header: develop
nav: api
sidebar: InnerAudioContext.offPlay
---


**解释**：取消监听 onPlay 事件

**方法参数**：Function callback

**代码示例**：

<a href="swanide://fragment/800b3a6986f8100cd5d091acd7c761cc1574013917868" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>

* 在 js 文件中

```javascript
Page({
    onLoad() {
        const innerAudioContext = swan.createInnerAudioContext();
        innerAudioContext.src = 'http://vd3.bdstatic.com/mda-ic7mxzt5cvz6f4y5/mda-ic7mxzt5cvz6f4y5.mp3';
        innerAudioContext.autoplay = false;
        innerAudioContext.onPlay(res => {
            swan.showModal({
                title: 'onPlay',
                content: JSON.stringify(res)
            });
            console.log('onPlay', res);
        });
        innerAudioContext.offPlay();
        this.innerAudioContext = innerAudioContext;
        this.innerAudioContext.play();
    }
});
```
