# flv-player

![pic](images/demo.jpg)

**本项目建立于2007年，是一个陈旧的.swf驱动的flv-player网页视频播放器。**

[打开演示页面](https://nihility-ming.github.io/flv-player/)

## 简介

**夜潭FLV播放程序**是一款FLV网络播放器，可以用于各种新闻系统或者blog系统,夜潭FLV播放程序拥有众多特点和自定义设置,经过不断升级
修正，已经具备用户需要的大多数基本功能。

## 功能

- 可以读取xml设置播放列表
- 多影片连续播放
- 自定义尺寸，自动适应
- 简洁播放器风格
- 自定义循环播放
- 支持最大化播放
- 支持直接js嵌入 智能双语互译


## 使用方法

关于根目录下的index.asp和index.htm文件,其实都可以作为首页使用!

### 读取影片xml

（请先打开根目录下的vcastr.xml）其中根目录下的vcastr.xml是播放列表的xml地址,不可以自行修改和添加播放列表。

如vcastr.xml里面的其中一行代码：
```
<item item_url="http://www.ruochi.com/product/vcastr/flv/happy_feet.flv" item_title="-幸福的
脚丫-预告片" />
```

这个是其中的一个节目，你可以在<vcaster></vcaster>之间添加多个（一行一个）！
例如

```
<item item_url="你的影片地址" item_title="你的影片名字" />
```

----

### 程序HTML代码

```
<object classid="clsid:D27CDB6E-AE6D-11cf-96B8-444553540000"
codebase="http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=6,0,29,0" width="240" height="120">
<param name="movie" value="vcastr22.swf">
<param name="quality" value="high">
<param name="allowFullScreen" value="true" />
<param name="FlashVars" value="vcastr_xml=vcastr.xml" />
<embed src="vcastr22.swf" allowFullScreen="true" FlashVars="vcastr_xml=vcastr.xml" quality="high"
pluginspage="http://www.macromedia.com/go/getflashplayer" type="application/x-shockwave-flash" width="240"
height="120"></embed>
</object>
```

----

### 高级选项

```
<param name="FlashVars" value="*" />

FlashVars="*"
```

`在以上2处*部分添加参数，使用 参数=值 的格式，多个参数用&连接，参数数量不限制`

例如

```
value="vcastr_file=http://www.transformersmovie.com/transformers_640.flv&vcastr_title=变形金刚预告
片&BarColor=0xFF6600&BarPosition=1"
```

表示影片地址是"http://www.transformersmovie.com/transformers_640.flv"，标题是"变形金刚预告片",控制栏颜色是0xFF6600，控制栏位
置在下方


```
<object classid="clsid:D27CDB6E-AE6D-11cf-96B8-444553540000"
codebase="http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=6,0,29,0" width="500" height="224">
<param name="movie" value="vcastr22.swf">
<param name="quality" value="high">
<param name="allowFullScreen" value="true" />
<param name="FlashVars" value="vcastr_file=http://www.transformersmovie.com/transformers_640.flv&vcastr_title=变形金刚预告
片&BarColor=0xFF6600&BarPosition=1" />
<embed src="vcastr22.swf" allowFullScreen="true"
FlashVars="vcastr_file=http://www.transformersmovie.com/transformers_640.flv&vcastr_title=变形金刚预告
片&BarColor=0xFF6600&BarPosition=1" quality="high" pluginspage="http://www.macromedia.com/go/getflashplayer"
type="application/x-shockwave-flash" width="500" height="224"></embed>
</object>
```

----

### 参数名称
参数说明	默认值
`vcastr_file` 方法2传递影片flv文件地址参数，多个使用|分开 空

`vcastr_title` 影片标题参数，多个使用|分开，与方法2配合使用 空

`vcastr_xml` 方法3 传递影片flv文件地址参数，样板参考 (根目录下的vcastr.xml 文件)

`IsAutoPlay` 影片自动播放参数：0表示不自动播放，1表示自动播放 0

`IsContinue` 影片连续播放参数：0表示不连续播放，1表示连续循环播 1

`IsRandom` 影片随机播放参数：0表示不随机播放，1表示随机播放 0

`DefaultVolume` 默认音量参数 ：0-100 的数值，设置影片开始默认音量大小 100

`BarPosition` 控制栏位置参数 ：0表示在影片上浮动显示，1表示在影片下方显示 0

`IsShowBar` 控制栏显示参数 ：0表示不显示；1表示一直显示；2表示鼠标悬停时显示；3表示开始不显示，鼠标悬停后显示 2

`BarColor` 播放控制栏颜色，颜色都以0x开始16进制数字表示 0x000033

`BarTransparent` 播放控制栏透明度 60

`GlowColor` 按键图标颜色，颜色都以0x开始16进制数字表示 0x66ff00

`IconColor` 鼠标悬停时光晕颜色，颜色都以0x开始16进制数字表示 0xFFFFFF

`TextColor` 播放器文字颜色，颜色都以0x开始16进制数字表示 0xFFFFFF

`LogoText` 可以添加自己网站名称等信息(英文) 空

`LogoUrl` 可以从外部读取logo图片,注意自己调整logo大小,支持图片格式和swf格式 空

`EndSwf` 影片播放结束后,从外部读取swf文件，可以添加相关影片信息，影片分享等信息，需自己制作 空

`BeginSwf` 影片开始播放之前,从外部读取swf文件，可以添加广告，或者网站信息，需自己制作 空

`IsShowTime` 是否显示时间 : 0表示不显示时间，1表示显示时间 1

`BufferTime` 影片缓冲时间，单位（秒） 2

## 使用协议

遵循MIT使用协议