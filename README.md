# videoPlayer
uniapp自定义播放器

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

**在index.vue中(简洁版)**  

~~~
<template>
  <div class="content">
    <chunlei-video :title="title" :srcList="srcList" class="video" ref="video" :gDuration="gDuration">
		
    </chunlei-video>
  </div>
</template>
~~~

## 完整版功能
1.包括简洁版功能

2.弹幕

3.下一集，选集

4.自动播放下一集

**在index.vue中(完整版)**  

~~~
<template>
  <div class="content">
    <chunlei-video :title="videoList[index-1].title" :srcList="videoList[index-1].srcList" class="video" ref="video" 
      :gDuration="videoList[index-1].gDuration" :episode="11" @playEpi="playEpi" :index="index" :danmuList="videoList[index-1].danmuList">
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
| episode | Number | 0 | 集数 |
| index | Number | 1 | 当前集数 |
| danmuList | Array | [] | 弹幕 |

## 事件

| 事件名 | 说明 |
| ---  | --- |
| playEpi | 跳到指定集数 |


## 如果觉得插件不错，麻烦给个好评

