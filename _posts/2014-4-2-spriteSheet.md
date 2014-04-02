---
layout: post
title: Avatar角色系统
tags:
    - Avatar
    - spriteSheet
---
# Avatar角色系统
最近总结webgame中的Avatar系统，有些心得跟体会，暂留纪录。
## Avatar角色主要需求

* 人物换装
* 人物动作

    * 站立
    * 行走
    * 攻击
    * 受伤
    * 打坐
    * 跳跃
    
## Avatar角色资源
一般情况下，Avatar可以采用以下资源形式：

* 直接使用flash中的MovieClip。
* 使用位图spriteSheet；

下面具体介绍一下两者大概情况。
### 使用MovieClip
使用MovieClip是最直接的方法。美术制作动画之后，直接使用导出的swf。程序通过MovieClip提供的方法控制swf的播放及停止。

此方法的优点是直接、方便。缺点是可能带来运行效率低的问题，特别是MovieClip层次嵌套较多的情况下。

### 使用spriteSheet
spriteSheet中文译名叫作精灵序列图。

网络上给出了相关定义，可以参考。
>spriteSheet主要是由N个图像组合成的一个大的图像，这个大的图像里面包括了一个完整动画的所有帧，使用一个大图片的好处就是减少读取次数。在一定数量的情况下，spriteSheet有很明显的优势

优势如下：

* 更小的文件尺寸
* 更快的打开速度
* 在FP11的时代可以借助STARTLING以便得到GPU的加速支持

一图胜过千言万语，还是上图吧。看看下图，就能大概明白，什么是spriteSheet了。

![spriteSheet](http://imgt1.bdstatic.com/it/u=978082466,2530970675&fm=23&gp=0.jpg)

spriteSheet广泛应用于各种类型的语言中，如cocos、flash等。应该可以说这是游戏的标准做法了吧。

使用spriteSheet的流程如下：

* 美术提供尺寸相等的动作序列图，或动作MovieClip
* 通过工具生成spriteSheet和配置文件

## spriteSheet生成工具
网上收集了些好用的spriteSheet工具，具体如下：

* `texturepacker` 这是最出名的工具了，功能非常强大，不过是英文版，同时还得付钱。当然喽，工具的作者也非常友好，可以申请一年的free license key。[点击下载](http://www.codeandweb.com/texturepacker)、[点击申请free license key](http://www.codeandweb.com/request-free-license)
* `sprite sheet editor` 国产软件，功能也是相当强大，而且是免费开源，并且作者还一直在更新此工具。真心感谢作者。[点击下载](http://zengrong.net/sprite_sheet_editor)
* flash cs6以上，就能够导出spritesheet了。这个也是非常不错的工具
* 最后，还可以自己写个工具，哈哈哈

如果还有其他的好工具，欢迎留言补充。

最后，还有个问题需要提一下。就是好多开发者想要利用别人的资源，比如说下载某个游戏的资源。但是发现别人的资源是经过处理的，已经进行了剪裁，每个图片的大小不一。如果直接使用这样的素材，会造成角色动作错位（抖动）形象。

一开始，也被这个问题困扰了好几天。最后也没想出什么解决的办法。因为如果还原已经剪裁的序列图，需要手工设置每张图片的基准点。除此之外，真没有想到其他办法了。

所以只能是通过寻找游戏里面的角色配置文件，通过这个配置文件还原角色的动作了。

另外，网上也有提到，可以使用序列图中，最大图的尺寸，将所有图片还原。这样应该会有点效果吧，有待尝试啊。


