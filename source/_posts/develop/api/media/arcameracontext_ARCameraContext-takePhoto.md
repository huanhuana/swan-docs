---
title: ARCameraContext.takePhoto
header: develop
nav: api
sidebar: arcameracontext_ARCameraContext-takePhoto
---



 

**解释**：拍照，成功则返回图片。


**方法参数**：Object object

**`object`参数说明**：

|参数  |类型 | 必填 | 默认值|说明|
|---- | ---- | ---- |---- |---|
|success| Function |   否  | |接口调用成功的回调函数|
|fail  |  Function  |  否 |  |接口调用失败的回调函数|
|complete |   Function  |  否  | |接口调用结束的回调函数（调用成功、失败都会执行）|

**success 返回参数说明**：


|参数名 |类型  |说明|
|---- | ---- | ---- |
|tempImagePath  | String | 图片的临时路径 |

 
**示例**：

<a href="swanide://fragment/c6b6e92b5ef4bc9276cfbc99fddf3dba1557733966512" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>

```js
Page({
    data: {
        photoSrc: ''
    },
    onShow() {
        const ARCameraContext = swan.createARCameraContext();
        this.ARCameraContext = ARCameraContext
    },
    takePhoto() {
        this.ARCameraContext.takePhoto({
            quality: 'high',
            success: res => {
                this.setData({
                    photoSrc: res.tempImagePath
                });
            },
            fail: res => {
                swan.showToast({
                    title: '请检查设备',
                    icon: 'none'
                });
            }
        });
    }
```