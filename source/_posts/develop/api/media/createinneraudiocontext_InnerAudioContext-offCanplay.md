---
title: InnerAudioContext.offCanplay
header: develop
nav: api
sidebar: InnerAudioContext.offCanplay
---


 

**解释**：取消监听 onCanplay 事件

**方法参数**：Function callback


**代码示例**：

<a href="swanide://fragment/89e680a27ba56865d88ddb9b113d5f6b1574014416962" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>

* 在 js 文件中

```javascript
Page({
    onLoad() {
        const innerAudioContext = swan.createInnerAudioContext();
        innerAudioContext.src = 'http://vd3.bdstatic.com/mda-ic7mxzt5cvz6f4y5/mda-ic7mxzt5cvz6f4y5.mp3';
        innerAudioContext.autoplay = false;
        innerAudioContext.onCanplay(res => {
            swan.showModal({
                title: 'onCanplay',
                content: JSON.stringify(res)
            });
            console.log('onPlay', res);
        });
        innerAudioContext.offCanplay();
        this.innerAudioContext = innerAudioContext;
        this.innerAudioContext.play();
    }
});
```