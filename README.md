<a href="https://github.com/lipangit/JiaoZiVideoPlayer" target="_blank"><p align="center"><img src="https://user-images.githubusercontent.com/2038071/42033014-0bf1c0b0-7b0e-11e8-811d-7639bcd294eb.png" alt="JiaoZiVideoPlayer" height="150px"></p></a>
--
<p align="center">
<a href="http://developer.android.com/index.html"><img src="https://img.shields.io/badge/platform-android-green.svg"></a>
<a href="http://search.maven.org/#artifactdetails%7Ccn.jzvd%7Cjiaozivideoplayer%7C5.8.2%7Caar"><img src="https://img.shields.io/badge/Maven%20Central-7.0.1-green.svg"></a>
<a href="http://choosealicense.com/licenses/mit/"><img src="https://img.shields.io/badge/license-MIT-green.svg"></a>
<a href="https://android-arsenal.com/details/1/3269"><img src="https://img.shields.io/badge/Android%20Arsenal-jiaozivideoplayer-green.svg?style=true"></a>
</p>

Q群: 490442439 2群: 761899104 验证信息:jzvd

微信公众号搜索: jzvdjzt [公众号文章](https://github.com/lipangit/JiaoZiVideoPlayer/wiki/%E5%85%AC%E4%BC%97%E5%8F%B7%E6%96%87%E7%AB%A0)

## 划重点
为了增加项目质量，促进项目进度，调用社群力量，方便社群管理，近日将推出基于以太坊erc-20的数字通证[JiaoZiToken(JZT)(饺子Token)](https://github.com/lipangit/JZT)，通俗点理解，谁给饺子视频播放器写代码、出主意、解决用户问题、活跃社群关系、关注项目进展，就给谁饺子Token。将来会让项目更加丰富，更加精致，必定大有可为。

[Wiki](https://github.com/lipangit/JiaoZiVideoPlayer/wiki)  [EnglishWiki](https://github.com/felipetorres/VideoPlayer-Wiki)  
[中文ReadMe](https://github.com/lipangit/JiaoZiVideoPlayer/blob/develop/README-ZH.md)  
[WorkPlan](https://github.com/lipangit/JiaoZiVideoPlayer/projects/2)  
[Weibo](http://weibo.com/2342820395/profile?topnav=1&wvr=6&is_all=1)  

## Features

1. You can completely customize the UI and any method
2. One line of code to switch the playback engine, supported video formats and protocols depends on the playback engine like:  [android.media.MediaPlayer](https://developer.android.com/guide/topics/media/media-formats.html), [IJKplayer](https://github.com/Bilibili/ijkplayer), [ExoPlayer](http://google.github.io/ExoPlayer/supported-formats.html).
3. Perfect detection of list sliding
4. Fullscreen and small window option available
5. Fullscreen works in multiple nested modes like ListView, ViewPager and ListView, ViewPager and Fragment
6. Can load, pause, play and other normal state into the fullscreen and exit fullscreen
7. A variety of video screen modes: full screen, you can cut full screen
8. Use of gravity sensors to automatically enter fullscreen
9. Gestures to control progress, volume and brightness in fullscreen mode
10. Home key to exit the interface to suspend the playback, return to the interface to continue playing
11. WebView Nested Local Video Controls
12. VideoCache in demo
13. PlayBack speed

## Steps for usage

1. Read through ReadMe
2. Download and install the demo apk[jiaozivideoplayer-7.0.1.apk](https://github.com/lipangit/JiaoZiVideoPlayer/releases/download/v7.0.1/jiaozivideoplayer-7.0.1.apk), each page enters once, each button clicks once
3. Download and debug the develop branch, and find the source code through the effect
4. See [custom-related WIKI](https://github.com/lipangit/JiaoZiVideoPlayer/wiki)，Realize your own needs

* [Getting Started Document 1](https://www.jianshu.com/p/4c187a09b838)
* [Getting Started Document 2](https://shimo.im/docs/xj5F85W1gqEEBXRJ)

## Screenshot 

![Demo screenshot][1]

[small window effect on list sliding](http://weibo.com/tv/v/FtxpWgqmg?fid=1034:5cda6fc7f394b403d592bd9b1d5a9701).

## Usage

Only five steps to use the player:

The 7.0.1 version is not very stable.

1.Import library:
```gradle
implementation 'cn.jzvd:jiaozivideoplayer:7.0.1'
```

Or download [aar](https://github.com/lipangit/JiaoZiVideoPlayer/releases/tag/v6.4.2) (not recommended).

2.Add `JZVideoPlayer` in your layout:
```xml
<cn.jzvd.JzvdStd
    android:id="@+id/videoplayer"
    android:layout_width="match_parent"
    android:layout_height="200dp"/>
```

3.Set the video uri, video thumb url and video title:
```java
JzvdStd jzvdStd = (JzvdStd) findViewById(R.id.videoplayer);
jzvdStd.setUp("http://jzvd.nathen.cn/c6e3dc12a1154626b3476d9bf3bd7266/6b56c5f0dc31428083757a45764763b0-5287d2089db37e62345123a1be272f8b.mp4"
                            , "饺子闭眼睛" , Jzvd.SCREEN_WINDOW_NORMAL);
jzvdStd.thumbImageView.setImage("http://p.qpic.cn/videoyun/0/2449_43b6f696980311e59ed467f22794e792_1/640");
```

4.In `Activity`:
```java
@Override
public void onBackPressed() {
    if (Jzvd.backPress()) {
        return;
    }
    super.onBackPressed();
}
@Override
protected void onPause() {
    super.onPause();
    Jzvd.releaseAllVideos();
}
```

5.In `AndroidManifest.xml`:
```xml
<activity
    android:name=".MainActivity"
    android:configChanges="orientation|screenSize|keyboardHidden"
    android:screenOrientation="portrait" />
    <!-- or android:screenOrientation="landscape"-->
```

## Details about UI and code customization

[See our Wiki](https://github.com/lipangit/JiaoZiVideoPlayer/wiki).

## Community

#### Group management

1. [熊晓清](http://blog.csdn.net/yaya_xiong) QQ:137048616
2. [Lionet](https://github.com/Lionet6?tab=repositories) QQ:2950527715
3. [montauk](https://github.com/hanmeimei888) QQ:958489121
4. [张展硕]() QQ:229431468

#### Questions and Answers

1. [熊晓清](http://blog.csdn.net/yaya_xiong) QQ:137048616
2. [の伤也快乐](https://github.com/jmhjmh) QQ:466278628
3. [吴亚男]() QQ:623562486

## Reward

![Reward][2]

## License MIT

Copyright (c) 2015-2018 李盼 Nathen

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

[1]: https://user-images.githubusercontent.com/2038071/31045150-a077cc8a-a5a2-11e7-8dc2-7a0e3a9f3e62.jpg
[2]: https://user-images.githubusercontent.com/2038071/29978804-45c321ba-8f75-11e7-9040-776d3b6dca1f.jpg
