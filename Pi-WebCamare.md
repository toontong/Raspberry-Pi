Raspberry-Pi 树莓派-摄像头篇
============
# 一、硬件
 
 - 罗技C270 - 带麦的。
 - 无牌子的，20～30元的烂货
 
# 二、软件

    网上搜索到是 motion 与 mjpg-streamer， 两者都有HTTP功能。直接apt-get安装。

## 2.1 关于[motion](http://pingbin.com/2012/12/raspberry-pi-web-cam-server-motion/)

- 配置项很多，很烦。
- 使用中CPU占用很高，我使用Chrome最新版，没法显示出图像，使用Pi内置的浏览器可以。
- 无声音
- 放弃

## 2.2 关于[mjpg-streamer](http://wolfpaulus.com/jounal/embedded/raspberrypi_webcam/)

- 配置很简单，二进制包，下载解压即用。
- CPU占用不高。
- Chrome依然不支持，使用[Video Lan Client播放器](http://www.videolan.org/vlc/index.html)能播放
- 局域网很流畅，流量比较大，延迟在1～2秒间。
- 无声音
- 杂牌摄像头报错：`The inpout device does not supports MJPEG mode` -- 不能用。 