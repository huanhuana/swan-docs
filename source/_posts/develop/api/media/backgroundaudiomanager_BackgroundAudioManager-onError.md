---
title: BackgroundAudioManager.onError
header: develop
nav: api
sidebar: BackgroundAudioManager.onError
---



**解释**：音频播放错误事件

**方法参数**：Function callback

**代码示例**：

<a href="swanide://fragment/01475be361811871bf712ade8fe010881573422974213" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>

* 在 js 文件中

```javascript

Page({
     onShow() {
        const backgroundAudioManager = swan.getBackgroundAudioManager();
        backgroundAudioManager.title = '演员';
        backgroundAudioManager.epname = '演员';
        backgroundAudioManager.singer = '薛之谦';
        backgroundAudioManager.coverImgUrl = 'http://c.hiphotos.baidu.com/super/pic/item/8b13632762d0f703e34c0f6304fa513d2797c597.jpg';
        backgroundAudioManager.onError(function(res) {
            console.log('backgroundAudioManager.onError', res)
            swan.showModal({
                title: 'onError success',
                content: JSON.stringify(res)
            })
        });
        this.backgroundAudioManager = backgroundAudioManager;
        this.backgroundAudioManager.src = 'http://vd3.bdstatic.com/mda-ic7mxzt5cvz6f4y5/mda-ic7mxzt5cvz6f4y5.mp3';
        this.backgroundAudioManager.play();
    }
});

```