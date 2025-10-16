# 《流量密码！AI幻术终极教程，3步做出百万爆款视频！》

> 来源：[https://ry5hwpuf7b.feishu.cn/docx/OQdZdGoXaorykxxIWpTc35Jenfc](https://ry5hwpuf7b.feishu.cn/docx/OQdZdGoXaorykxxIWpTc35Jenfc)

《流量密码！AI幻术终极教程，3步做出百万爆款视频！》

各位好，我是吴东子

所谓AI幻术，就是用AI技术生成让人看起来像中了幻术一样的图片

这类内容因为「新奇有趣」的特性，在短视频平台快速爆火，出现了非常多百万、千万级播放的爆款作品

用AI技术把火过的梗或者表情包再做一遍，就是当下的流量密码

我花了几天的时间，把AI幻术的所有的玩法都研究了一遍，整理出了一套完整的制作流程

文章包含了抠图，SD基础设置，Controlnet设置三个步骤，只要大家一步一步跟着操作，也可以做出同款的AI幻术

1.风景幻术

2.二次元幻术

3.建筑幻术

4.表情包幻术

另外，文中需要用到的模型文件，也都给大家打包好放在末尾的网盘链接里，不需要大家再自己到处去找

花了很多时间才整理出来，希望对你有帮助

严禁抄袭搬运，势必追诉到底！

# 一、AI幻术是什么

AI幻术可以把你想要的元素，隐藏到一张看似普通的图片里

表面看似正常，实则 “暗藏玄机”

像这张，放大看图片的每一个区域都还算正常，但当图片缩小的时候，就可以看到一个熟悉的男人

![](img/781e0e93cb58f0f0895c499087d0dff3.png)

除此之外，还有这样的街景图

![](img/d22d5723aa92495ca3cbf5b8157adb98.png)

![](img/4270a9f1ac8ccc71ffbcba38e6846db2.png)

风景图

![](img/a8d83f7ca2911fc89a1ecd32d568d0de.png)

![](img/b48da00cd0cd545c12c0ba557cc044ee.png)

甚至还有二次元的美女、小猫咪、一座房子，都可以看到那个男人的身影

![](img/07fa67fb0f7c310740da5c4ab6d414c6.png)

![](img/1a793372bb8bfdf55ad46500bdf1b45c.png)

![](img/5384a3d563b2aff9ef02849e49d2b2f1.png)

更好玩的是，变成视频之后，那个男人直接跳起舞来了

这些有趣的图片跟视频，有些博主把他发到抖音上就获得了几十万的点赞，在b站甚至有上百万的播放

![](img/8919902f350f561eca7fa0dd7a9bd1f4.png)

![](img/312808c144e8dfac5c55524e5d019692.png)

而以上这些千变万化的图片和视频，通过AI绘画只需要三步就能做出来

那今天这篇文章就带大家一步步操作，做出来这些有趣的AI幻术图片和视频

# 二、三个步骤，快速生成AI幻术图片

制作坤坤的AI幻术图可以分为以下三个步骤

1.抠图

2.SD基础设置

3.controlnet设置

接下来我们就以这张城市夜景图为例，看看具体的操作步骤

![](img/1a212b271efd7c982f444787db387c52.png)

## 1.抠图

找一张自己想要制作的图片，抠出黑白蒙版图，这个蒙版图在后面的controlnet设置需要用到

![](img/75b072930180e77a8bff966fbd5d7a50.png)

![](img/d23e63c0d7c758501337eaba0ceae719.png)

我们抠图用会用到SD的一个抠图插件——segment anything

### SD抠图插件——segment anything使用方法

插件从安装到使用分为三步

01.安装插件

02.安装模型

03.抠图

01.安装插件

插件的安装十分简单，我们只需要：

①打开SD，点击拓展

②点击可下载

③点击加载拓展列表

④在搜索下面输入“segment”

⑤点击安装

![](img/73c6b11180ed2289fc54e521a4e9f9f6.png)

02.安装模型

Segment anything还需要一个模型，大家只需要下载网盘里的“sam”文件夹

然后把文件夹里的模型放到对应的文件夹

存放位置：SD文件夹\extensions\sd-webui-segment-anything\models\sam

![](img/d7de4c6e60a339c37a6571ff843a5881.png)

安装好了之后，我们再打开拓展，点击“应用更改并重启”，这样插件的页面才能显示出来

![](img/362b4f4bf1288d186a4ed9a45a3f76b6.png)

03.抠图

这时候回到SD，在点击“segment anything”打开插件的页面，

![](img/15c11819a128c3fbd57e586d9ee6f112.png)

上传一张我们需要抠图的照片

![](img/0361d85d0cbc2ce95870335303719255.png)

鼠标左键点击会生成黑色的点，就是我们要抠出来的部分，可以围绕人物点一圈

鼠标右键点击会生成红色的点，就是我们不要的部分

![](img/8c5629617323978d00e004a0c0df0a31.png)

给图片打好点之后，就点击 “预览分离结果”，就可以生成蒙版图片了

![](img/f394ff27ef80d92b71d40067fc3f18fb.png)

一次会抠出来三组图片，选一张扣的最完整的保存下来

如果三张都不完整，再去多打几个点，重新分离

![](img/e261e022660dbccf1933e9f88680e071.png)

到这里我们的图片就处理好了，接下来就可以用这个蒙版图去生成图片

## 2.SD基础设置

SD的基础设置包括：

01.选大模型

02.写关键词

03.设置参数

### 01.选大模型

可以选二次元的、也可以选写实的

像这张城市夜景图用的就是写实的大模型

![](img/a929473d64f42c11a91661da0688bdc3.png)

如果没有这个大模型的小伙伴可以在网盘里面下载majicmix的文件夹

把文件夹里的大模型复制到SD文件夹，放到”models“里的”Stable-diffusion“文件夹

存放位置SD文件夹\models\Stable-diffusion

![](img/ffa8b5fc0955d62a3a55e8f82b4dee32.png)

### 02.写关键词

关键词需要大家多尝试

通过不断出图的积累形成自己的词库

这也是我跑了很多次后发现出图比较稳定的城市夜景关键词

大家可以直接照抄

城市夜景关键词：

The highest quality, masterpiece, high-definition image quality, rich details,

City night view, Road,cars,architecture, streets, transportation, bustling city, lighting, plants,Water, Reflection,Sky, clouds,Colorful lights, headlights

最高的质量，杰作，高清画质，丰富的细节，

城市夜景、道路、汽车、建筑、街道、交通、繁华城市、灯光、植物、水、倒影、天空、云朵、五颜六色的灯光、车灯

通用负面关键词：

EasyNegative, ng_deepnegative_v1_75t, badhandv4,(worst quality:2), (low quality:2), (normal quality:2), lowres, ((monochrome)), ((grayscale)), bad anatomy,DeepNegative, skin spots, acnes, skin blemishes,(fat:1.2),facing away, looking away,tilted head, lowres,bad anatomy,bad hands, missing fingers,extra digit, fewer digits,bad feet,poorly drawn hands,poorly drawn face,mutation,deformed,extra fingers,extra limbs,extra arms,extra legs,malformed limbs,fused fingers,too many fingers,long neck,cross-eyed,mutated hands,polar lowres,bad body,bad proportions,gross proportions,missing arms,missing legs,extra digit, extra arms, extra leg, extra foot,teethcroppe,signature, watermark, username,blurry,cropped,jpeg artifacts,text,error

### 03 .基础参数

宽度和高度根据自己的图片比例去调整

![](img/6d1cf17af81a13b017a7fb7ad8a0819e.png)

## 3.controlnet设置

我们先把刚刚保存的蒙版图拖到图像的框里

然后选用qrcode monster模型，如果没有这个模型的小伙伴可以自行安装

模型放在网盘，存放位置：sd文件夹\models\ControlNet

控制权重0.75~1.5，权重越大，人物轮廓越清晰

![](img/18c504460e77cad0fc4175b8d4eb73cc.png)

最后点击生成

你的第一张AI幻术图片就做好了

![](img/649d4126a06a0dc7954127943a8cc142.png)

![](img/c126fb81ae3497485a6940292f8d4964.png)

![](img/59f8b95eeaf154e153aee9202f4e732d.png)

![](img/28dc69d7deb723a4d9f158b88608adf3.png)

![](img/f6e7e8677d7b70ada9f58f7c7e23a1a2.png)

![](img/189254d1dd76f4b0f9f98a0a4ef65070.png)

以上就是关于AI幻术图片的制作方法

为了方便大家能够制作各种不同风格的AI幻术图片

我这几天花了很多时间把市面上比较热门的类型都跑了一遍，出了几百张图后

终于给大家整理出了几套即好用，而且出图比较稳定的关键词

都已经打包好放在网盘里了，大家可以直接抄作业

## 4.不同类型图片关键词

### 风景图

关键词：

The highest quality, masterpiece, high-definition image quality, rich details,

Mountains, blue sky,clouds, plants, trees,lake, beautiful scenery

最高的质量，杰作，高清的图像质量，丰富的细节，

山，蓝天，云，植物，树木，湖泊，美丽的风景

![](img/57215ddb4e7bd4f0fd7861c84e73c2ed.png)

![](img/d9447f7001e910aeebbdd9c59525817b.png)

![](img/fbb03dfcacfb9212a27f82931423d42d.png)

如果想让人物轮廓看起来更加明显

可以生成这种人物轮廓是黑色的图片

![](img/9e2e92858fdfb69979dc5314970d0df2.png)

![](img/0475b67e6deb8f9be93d7b728f658fe4.png)

![](img/24ed03bc24e2a2d951809589593eee58.png)

只要在controlnet设置里，预处理器选择invert，就可以把黑白区域反转过来

![](img/1d7a1d77a3b6024b7208b12f4e98b2a9.png)

### 二次元女孩

关键词：

The highest quality, masterpiece, high-definition image quality, rich details,

1 girl, delicate facial features, big eyes, long hair,

Dress, exquisite clothing,

Upper body, with a garden in the background

最高的质量，杰作，高清的图像质量，丰富的细节，

1个女孩，精致的五官，大眼睛，长发，

连衣裙，精致的服装，

上半身，背景为花园

![](img/291a94b500a0dc7712a627631c688184.png)

![](img/40cae067c74bef12e568e296276fd9fe.png)

![](img/4bd32c692a32fe3d01e8a8a48cd361f2.png)

### 房子

关键词：

The highest quality, masterpiece, high-definition image quality, rich details,

1house, yard, residence,outdoors

最高的质量，杰作，高清的图像质量，丰富的细节，

1房子、庭院、住宅、户外，

![](img/373e1cab756dfa4e25bfe348d0909284.png)

![](img/ad3f3029b165cb9c6d72fe46b1e402cc.png)

![](img/14773d9f7c9bcf177243134ed3358b59.png)

### 表情包

除了坤坤以外，我们还可以各种有趣的图片

姚明的表情包

![](img/a74e1f815869f21732dc535d832a2bb3.png)

![](img/bba031e4fc1646f2bbb3c4b9c489e0e4.png)

像姚明的表情包这种需要五官形状的图片就不需要扣蒙版图了

直接把原图上传到controlnet

控制权重拉高一点，这样出来的图片轮廓就会很清晰了

![](img/aa6e1f50118aa66b2ae6951c193773f4.png)

用AI幻术结合当下热点或者比较火的梗，这样视频的流量也会更大

# 三、AI幻术视频怎么做

做AI幻术视频其实跟做图片是一样的，因为视频就是由无数张的图片组成

只不过这一次从生成一张照片变成了批量化生成无数张照片

这时候我们的操作步骤就变成：

1.批量化抠图

2.批量化出图

3.剪成视频

做出来的效果是这样的

接下来我们看看具体的操作

## 1.批量化抠图

首先我们需要先把视频变成无数张照片，再生成这无数张照片的蒙版图

具体分为三步：

01.安装插件

02.将视频转换成照片

03.生成这些照片对应的蒙版图

### 01.安装插件

这个插件可以直接把视频分成无数张照片，并且生成对应的蒙版图

安装操作十分简单：

①.点开“拓展”

②.选择从“网址安装”

③.在第一行把网址复制进去，https://github.com/ClockZinc/sd-webui-IS-NET-pro.git

④.点击安装

![](img/167abda1945bdb96702a409ac192d72a.png)

把网盘里《IS-Net》文件夹里的模型装到下面的位置

储存地址：sd文件夹\extensions\sd-webui-IS-NET-pro\saved_models\IS-Net

![](img/de824cecbb4fc3a24125b19241074d23.png)

这样我们的插件就安装好啦

### 02.将视频转换成照片

①.重新启动stable diffusion，在状态栏里就可以看到我们新装的插件——isnet_pro

②.打开isnet_pro的页面

③.把视频拖进方框里

④.打开启用输出帧率控制，输出帧率设置为10，输出帧率设置得越高，出来的图片就越多，为了节省时间，这里设置了10帧，也就是一秒视频出十张图片

⑤.新建一个文件夹，把文件地址复制到“图片输入地址”，用来存放生成的照片，注意文件夹的名字不要有中文

⑥.最后点击“gene_frame”生成

![](img/f3905b845a13e51fecef9582c2c1defb.png)

复制文件地址的方法：

鼠标右键点击文件夹，点击“复制文件地址”

![](img/8ee65cad8ac395b80cfc61fc742dea2f.png)

接着把文件地址复制进去

注意，要把前后的双引号删掉，不然会报错

![](img/3d596cad909dfd4a417f4a72124306c5.png)

照片处理完了之后，就可以在文件夹里看到截出来的所有图片

![](img/72bbf31e55a145912189ca1eba433e11.png)

接下来我们就要给这每一张图片生成对应的蒙版图

### 03.生成照片对应的蒙版

①.打开“ISNETpro2”的页面

②.把前面存放照片的文件夹地址复制到“图片输入地址”

③.再新建一个文件夹，用来存蒙版图，把地址复制到“图片输出地址”注意文件的名字不要有中文

④.最后点击“仅生成蒙版”

![](img/9b7f0a285df04dbf9a3baabecc914b0a.png)

这时候处理完的图片就是这样的黑白蒙版

![](img/64827512a8237568b71bd33ff9a0dddd.png)

到这里全部图片就处理好啦，接下来就是生成图片

## 2.批量化出图

出图这一步跟前面只生成一张照片是一样的，大模型、关键词、参数都一样

只是在controlnet里面选择批量出图

01.打开ControlNet，设置不变，点击“批量处理”

02.把黑白蒙版图片的文件路径复制黏贴到”输入路径”

03.点击生成

这里大家可以先用单张蒙版图测试一下出来的效果，确保所有参数设置没有问题就可以开始批量出图了

![](img/8f7aef0b8582aed8a580db0d1c6e3a55.png)

根据自己照片的张数、设置的分辨率和迭代步数不同，出图的时间不同

耐心等照片生成就可以了

## 3.拼接成视频

等全部照片生成好了之后，我们就可以剪成视频了

点开文件夹“📂”图标，在里面找到我们刚生成好的照片，存到一个新的文件夹里面

注意新建的文件夹不要有中文字符

![](img/30d75c0e2affd37319904367f2646b08.png)

接下来打开 isnet-pro 插件，把图片拼接成视频

帧率设置为 10

把刚刚新建的文件夹地址复制到 “输入地址"

再复制一个存放视频的文件夹地址

最后点击生成

![](img/b65a0768dd8d248a9c515a12f9aabfb1.png)

最后我们只需要在剪映加上自己喜欢的BGM就可以了

再看一次最终的成片

# 四、结尾

好了，以上就是我们这篇文章的全部内容，希望能够让你做出更多有趣好玩的AI幻术图片

如果你对AI感兴趣的话，可以关注我的公众号：吴东子AI，也欢迎分享给你身边想学AI技术的朋友

里面有我之前发过的所有文章，之后也会持续给大家更新实用的AI干货教程

我是吴东子，用奶奶都能听懂的方式，分享可以落地实操的干货，我们下篇文章再见！

网盘链接：https://pan.baidu.com/s/19Xnof-BSA-FubkMc_0XNhA?pwd=wdz6

提取码：wdz6

吴东子AI账号简介：https://ry5hwpuf7b.feishu.cn/wiki/space/7283841978071072772?ccm_open_type=lark_wiki_spaceLink