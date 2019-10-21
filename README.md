# videoPlayer
uniapp自定义播放器

## 说明

1.插件在uni-app编译模式下编写，在 manifest.json 的源码视图里切换模式， manifest.json -> app-plus -> nvueCompiler 切换编译模式。

2.下载管理不在组件里，具体看项目示例

3.安卓下调整亮度时，视频会黑屏一下报了 [bug](https://ask.dcloud.net.cn/question/80969)

## 使用方式

**在index.js中**  

~~~
import chunleiVideo from '../../components/chunlei-video/chunlei-video.nvue'
components:{chunleiVideo}
~~~

## 简洁版功能
1.全屏

2.双击暂停或播放

3.进度,音量，亮度控制

4.高清切换

5.倍速

6.强制全屏

7.循环播放

8.锁屏

9.主题颜色切换

**在index.vue中(简洁版)**  

~~~
<template>
  <div class="content">
    <chunlei-video :title="title" :srcList="srcList" class="video" ref="video" color="#c93756" :gDuration="gDuration">
		
    </chunlei-video>
  </div>
</template>
~~~

## 完整版功能
1.包括简洁版功能

2.弹幕

3.下一集，选集

4.自动播放下一集

5.下载管理

6.初始播放位置

**在index.vue中(完整版)**  

~~~
<template>
  <div class="content">
    <chunlei-video 
    	ref="video"
 	class="video"  
	:episode="11" 
	:index="index" 
	color="#c93756"
	@playEpi="playEpi" 
	:downloadBtn="true"
	@clickDownload="clickDownload"
	:title="videoList[index-1].title"
	@fullscreenchange="fullscreenchange"
	:srcList="videoList[index-1].srcList" 
	:download="videoList[index-1].download"
	:gDuration="videoList[index-1].gDuration" 
	:danmuList="videoList[index-1].danmuList" 
	:initialTime="videoList[index-1].initialTime"">
    </chunlei-video>
  </div>
</template>
~~~

## OBJECT参数说明

| 参数 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| srcList | String,Array | '' | 播放视频的资源地址 |
| title | String | '' | 视频标题 |
| gDuration | Number | 0 | 总时长 |
| color | String | '#FF6022' | 主题颜色 |
| episode | Number | 0 | 集数，为默认值时不显示选集，下一集 |
| index | Number | 1 | 当前集数 |
| danmuList | Array | [] | 弹幕,为默认值时不显示按钮 |
| initialTime | Number | 0 | 初始播放位置 |
| downloadBtn | Boolean | false | 下载按钮 |
| download | Boolean | false | 下载状态 |

## 事件

| 事件名 | 说明 |
| ---  | --- |
| playEpi | 跳到指定集数 |
| clickDownload | 点击下载 |


## 如果觉得插件不错，麻烦给个好评

