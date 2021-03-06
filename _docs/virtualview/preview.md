---
title: "编译工具使用"
permalink: /docs/virtualview/preview
excerpt: "编译工具使用"
modified: 2018-03-05T20:05:12-04:00
sidebar:
  title: "VirtualView预览工具"
  nav: virtualview-docs
---

## Android

### 下载工具：
地址及演示：[github](https://github.com/alibaba/virtualview_tools/tree/master/compiler-tools/TemplateWorkSpace/android-tool)

### 简介
本脚本基于 `buildTemplate.sh` 脚本，整合了『编译』-『上传』-『刷新』的流程。目的在于让模板编写之后自动刷新预览。

### 依赖环境
+ python
+ adb
+ Java

### 使用方法

`python buildAndPreview.py VH2Layout`

参数是模板名称，也就是当前要修改、预览的模板，与 `templatelist.properties` 里的名称一致。

### `previewconfig.conf` 配置参数

+ 推送编译后的 .out 文件到手机存储目录下：

#模板推送到手机存储的路径

```
[path]
target = /sdcard/com.tmall.wireless.virtualviewdemo/virtualview/
```

+ 预览app的预览界面

```
[preview]
activity = com.tmall.wireless.virtualviewdemo.debug/com.tmall.wireless.virtualviewdemo.PreviewActivity
```

以上默认值都是基于 VirtualView-Android 的 [demo](https://github.com/alibaba/Virtualview-Android/) 里配置的，可以自行迁移 demo 代码到自己的 app 环境中进行预览。

### 预览客户端
默认基于 VirtualView-Android 的 [demo](https://github.com/alibaba/Virtualview-Android/)，当有自定义控件的时候，需要修改预览 app 里，添加自定义组件注册逻辑，因此建议参考 demo 配置自己的预览环境。(注意确保手机有读SD卡权限)
