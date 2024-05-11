# 如何使用SD批量生成小红书爆款顶流图片？【极简版】

> 来源：[https://wurchmz1an.feishu.cn/docx/XiwmdQFijotSRAxrBv8c1dLmndr](https://wurchmz1an.feishu.cn/docx/XiwmdQFijotSRAxrBv8c1dLmndr)

要说小红书3月份最火爆的头像壁纸图片是哪个？

那非 流光女孩 莫属了

让我先看一下用这个模型的出图效果

![](img/ac9fc3740b4bcd6119808197fd0e2348.png)

![](img/07b00f763584bafc4f341de9f0cc5d9d.png)

![](img/347f39ab7377b39e0b7a5cb2f30fddbf.png)

![](img/bd817ca618cc0bd1e25204bd801c9c25.png)

是不是非常时尚且养眼呢？

而以女性用户为主的小红书来说

这类头像壁纸的涨粉与吸金能力也很强！

## 强劲的变现能力

例如，在3月15日，小红书用户子鱼哎吖发布了首篇笔记

不到1个月内，粉丝数量达到了1.7万，获得了5.1万的点赞和收藏。

![](img/ee2f0093929a40b02b9e26acc89c4d4b.png)

而他的变现模式主要有

1：知识付费

2：私人高级订制

3：小红书店铺售卖图片

![](img/e48852b583972d5240b20d1206bef805.png)

销量排名第2的猫耳少女共计营业额为 418.6元

问了一下作者，累计月收入已过万

而另一位更为厉害的小红书作者橘鹿

更是在短短3天内粉丝便增加了2万粉

![](img/1c4729147f3057dcb8f004d7314626a3.png)

他的收益更高

不但开了3个收费的社群

更是有自己的垂直类穿搭教程

和作者聊了下收益已达6位数/月

![](img/2326b3e1ff12f9e046d7e9c3f9291b52.png)

## 小程序的弊端

说完了收益，浅谈一下AI制图软件

这些漂亮的小姐姐均是由一些小程序AI绘图制成

虽然这些小程序出图很便捷

但却存在非常多的弊端

### 1：速度慢

如果不是普通会员需要排队，可能做一幅图需要5分钟。

作者最长一次是一张图等了45分钟

就果断放弃使用小程序来制图

![](img/406af434036bc2b4b3303e46a683f98d.png)

![](img/c39814fdcb590d4793ff9f0dd8685299.png)

### 2：数量少

如果不充会员，每天就只能画5幅左右

### 3：耗时间

如果每天我们要发20篇笔记，每次5分钟 ，也要接近1小时40分钟。

而我知道的是，此类头像号作者

每天都要花很长时间在制图上

![](img/c7492acb2762adf9c4a5445356efc02d.png)

那有没有什么方法，可以高效且经济的解决这个问题呢？

经过一段时间的调试

总算找到了不吃电脑配置

且较为经济的解决方案

## 经济高效的解决方案

这次我们要使用的Stable Diffusion，它是2022年发布的深度学习图像生成模型。

简单来说，就是你输入文字，它就会根据文本的描述产生详细的图像。

由于本地端的部署非常麻烦，又要下载、又要弄python、还要弄Git库。

并且如果你家的显卡显存很低，跑20张高清图可能就需要45分钟（6G显存）

现在的显卡又非常昂贵、像4090 24G的显存就要过万。

配置符合40490的CPU与显示器价格也朝着3W奔去。

所以我们这次的目的就花几块钱，体验下 24G显存显卡的魅力！

## 一键部署云端Stable Diffusion

整体的流程大致分为四步

1：注册平台

2：上传制图模型

3：一键云端部署 Stable Diffusion

4：生成图片

![](img/3934bdd3a717e0b93e7336d805297ad5.png)

# 一：注册平台

注册链接：https://www.lanrui-ai.com/register?invitation_code=4106

注册时填写邀请码 ：4106并关注公众号：揽睿星舟 ，扫码添加客服领取福利金

如果不要免费的时长，可以跳过关注公众号这个步骤

### 2：创建工作空间

进入控制台

![](img/a33b7f2fe5b94ba6c6268a2d19023d47.png)

![](img/312fe5c3573334d9bd5a36f18438d783.png)

目前平台在搞活动，有优惠，3090-24G 只需要 1.9元1小时

![](img/35bcfb8b13072b14815d452796ac33c8.png)

点击使用后，名称自己取，我选取的是默认

运行环境镜像选择 公有镜像 / others / sd-webui-2.0 / v3

数据集选择 sd-base

![](img/c4abca02a0045c1bce9da0659683feab.png)

待实例状态为运行中后，进入Jupyter后， 运行如下命令。

![](img/93cebb3d50f42bf54a3791d649e3967d.png)

![](img/402765e177e5425eaf03a1fd9efb2a11.png)

![](img/5e917df01f388458a51aa3d0f94855ba.png)

// Some code

cd /app

bash start.sh

![](img/5aa514afad4a27d981e393a70b580fb9.png)

然后在实例-操作列中，复制调试地址，粘贴到浏览器后就能访问Stable Diffusion Web UI

云服务 1小时起用，也就是2块钱。不要开了关，关了开。反而费钱

![](img/572d989b807f619925f1c0fd53b57ee2.png)

复制调试地址，新建一个网页，这样就进入SD的 Webui了

# 二：上传制图模型

如果是第一次启动的话，先执行第三步 创建应用

这样文件夹才会显示

本次采用新的网盘类上传与下载方法

网盘上传下载小妙招

下面以windows系统为例

安装 Cyberduck，安装好之后是没有桌面程序显示的

需要点击windows左下角搜索Cyberduck 能找到应用

如果没有找到就去开始菜单栏，全部应用里找

![](img/0365303979ff516d24887f21abe27f3d.png)

![](img/39b2a55689e641751e085a7939fa87ec.png)

新建链接，更多选项

![](img/11f65351adf8fb4474071018d707489d.png)

找到 AWS PrivateLink for Amazon S3，并勾选服务

![](img/e7f3afa3182acdc31f1a4dd1df6a53a9.png)

关掉这个页面，回到首页新建链接

![](img/ebdb7ca3deb10cc7d7406ae1c43f25cc.png)

服务器链接地址：在星舟的官网左侧，点击网盘→命令行→，命令行HTTPS://后面那串东西复制过来

![](img/c89ffcf6cfe6c98c281f3cd348ca45a6.png)

访问密秘和私钥的的信息在官网头像下方的设置里

![](img/b6d4d4415e993b9c7b9c0dec0522aa72.png)

找到 AK SK 把 账号和密码复制过去

![](img/bc7fb5755f591abd3335ac69a2b60fd6.png)

这样我们就可以像百度网盘一样上传和下载文件

再也不用命令行了

![](img/a7edc46ae28ae124eb2403db03f0906c.png)

## 上传制图模型

这次我们需要的模型是大模型是YesMix-V1.5.safetensors

loar皮肤是 fashionGirl_v50.safetensors

YesMix-V1.5.safetensors下载地址

fashionGirl_v50.safetensors下载地址

YesMix-V1.5.safetensors 需要放在models/stable-diffusion这个文件夹中

![](img/0ce98d05ae588f9705742ed9047853d3.png)

fashionGirl_v50.safetensors 需要放在medels/lora里

![](img/c9343c26c019d970b88001b8799256ce.png)

# 四：生成图片

在设置中 stable diffusion → SD VAE 选择None

VAE就是滤镜

![](img/3690cf4994f2608aac57c8e4d7285fd9.png)

选择 yesmix 模型 → TAG里添加 < lora:fashionGirl_v50:1>，把前面的空格去掉

![](img/a58efdaa8b83f16b92d0c1e898382650.png)

如果想做出文章一开始的那种图片

原图下载链接

![](img/f19082d778970b3c8f6966fe179c739f.png)

直接把图片放到 png info，然后send to txt2img，就可以了。

如果觉得这篇攻略对你有帮助，欢迎给个免费的赞！谢谢