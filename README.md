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

**在index.vue(简洁版)中**  

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

**在index.vue(完整版)中**  

~~~
<template>
  <div class="content">
    <chunlei-video :title="videoList[index-1].title" :srcList="videoList[index-1].srcList" class="video" ref="video" 
      :gDuration="videoList[index-1].gDuration" :episode="11" @playEpi="playEpi" :index="index" :danmuList="videoList[index1].danmuList">
    </chunlei-video>
  </div>
</template>
~~~

## OBJECT参数说明

| 参数 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| type | String | default | modal类型：default，select，advert，share，input，custom |
| value | Boolean | false | 是否显示 |
| maskEnable | Boolean | true | 是否点击遮罩退出 |
| mData | Object, Array | Object | 数据 |
| navMask | Boolean | 否 | 是否遮住导航栏 |
| nav | Boolean | true | 该页面是否有导航栏，存在时遮住 |

**mData数据示例**  

~~~
defaultData:{title:'提示',content:'这是一个模态弹窗',cancelText:'cancel',confirmColor:'#3CC51F'},
selectData:[{title:'拍摄',content:'照片或视频',icon:'../../static/shoot.png'},{title:'从照片选择'}],
advertData:{src:'../../static/advert.jpg',width:'600rpx',height:'350rpx'},
shareData:[
  {title:'朋友圈',icon:'../../static/pengyouquan.png'},
  {title:'微信好友',icon:'../../static/weixinhaoyou.png'},
  {title:'微博',icon:'../../static/weibo.png'},
  {title:'QQ好友',icon:'../../static/QQhaoyou.png'},
  {title:'QQ空间',icon:'../../static/QQkongjian.png'}
 ],
inputData:{
  title:'登录',
  content:[
  {title:'手机号',content:'',type:'number',placeholder:'请输入手机号'},
  {title:'密码',content:'',type:'password',placeholder:'请输入密码'}
  ]
}
~~~

## 事件

| 事件名 | 说明 |
| ---  | --- |
| onConfirm | 用户点击了确定按钮 |
| onCancel | 用户点击了取消按钮 |

如果觉得插件不错，麻烦给个Star [gitHub](https://github.com/15157757001/uniapp-modal)

