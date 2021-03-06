---
title: InnerAudioContext.offWaiting
header: develop
nav: api
sidebar: InnerAudioContext.offWaiting
---



**解释**：取消监听 onWaiting 事件

**方法参数**：Function callback

**代码示例**：

<a href="swanide://fragment/daf22706411859f65d6218bf078944071574013156111" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>

* 在 js 文件中

```javascript
Page({
    onLoad() {
        const innerAudioContext = swan.createInnerAudioContext();
        innerAudioContext.src = 'http://vd3.bdstatic.com/mda-ic7mxzt5cvz6f4y5/mda-ic7mxzt5cvz6f4y5.mp3';
        innerAudioContext.autoplay = false;
        innerAudioContext.onWaiting(res => {
            swan.showModal({
                title: 'onWaiting',
                content: '正在加载，请耐心等待'
            });
            console.log('onWaiting', res);
        });
        innerAudioContext.onEnded(res => {
            innerAudioContext.offWaiting();
        });
        this.innerAudioContext = innerAudioContext;
        this.innerAudioContext.play();
    }
});
```