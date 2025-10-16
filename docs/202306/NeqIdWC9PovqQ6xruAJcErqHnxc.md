# 《ControlNet终极攻略》

> 来源：[https://ry5hwpuf7b.feishu.cn/docx/NeqIdWC9PovqQ6xruAJcErqHnxc](https://ry5hwpuf7b.feishu.cn/docx/NeqIdWC9PovqQ6xruAJcErqHnxc)

《耗时7天，终于把15种ControlNet模型搞明白了！》

各位好，我是吴东子

我的所有资料都在公众号「吴东子AI」

这篇文章是SD三部曲的第三篇——「ControlNet的终极攻略」

前面我们说到如果想真正把SD应用起来，最重要的两个功能是：Lora和ControlNet

Lora负责把想要画面的“主体”或“场景”炼制成模型

ControlNet负责更好地“控制”这个“模型”或画面

Lora教程之前已经出了，感兴趣的朋友可以去翻看

ControlNet一共有15种模型，每种模型对应不同的采集方式，再对应不同的应用场景，每种应用场景又有不同的变现空间

我花了一周时间彻底把15种模型研究了一遍，跑了一次全流程，终于写完了本文

文章包含了ControlNet的功能介绍，安装方法，模型采集方式，实操案例，以及下面几个目前很好玩的功能

1.动漫转真人

2.真人转动漫

3.控制人物姿势、表情

4.线稿AI上色

5.固定主角

大家只要跟着一步一步操作，一定能学会

另外，需要用到的整合包和模型也都给大家打包好放在网盘（链接在文章末尾）

花了很多时间才整理出来，希望对你有帮助

严禁抄袭搬运，势必追诉到底！

# 一、ControlNet究竟能干什么？

## 1.控制人物姿势

能控制生成的人物的姿势、表情，甚至是每一根手指的骨骼

![](img/9bfc8fc88fd05e70a90e37960f9cc03b.png)

![](img/6cf6dddf23db5e7eb3872e51be8772a1.png)

## 2.线稿上色

![](img/a5731657b91104cf91463286e31c2981.png)

![](img/17f6102ee6b47ffe9d0e05a969d1fa75.png)

![](img/48683f4a984856b4bbde314f4fc06f56.png)

![](img/9b1da3e81da639ef6b730a9adbcda2aa.png)

## 3.恢复画质

![](img/89bafc7daba852ce4686fd607746056a.png)

![](img/fffe22e05c0ec5ae53ca13687895d8a1.png)

## 4.动漫变真人

![](img/95287a72d9aee8c3bd89e77c5ba7572d.png)

![](img/c75be5b0e222f101d2cd55d548d1cfe5.png)

controlnet还有非常多的功能用法，具体用法会在后面的文章里面详细去讲

# 二、ControlNet是什么

AI绘画最终要实现的目标——让出的图与我们脑海里想象的画面一致

但目前现状是：随机性太强

很多时候能不能出来一个好看的画面，只能通过大量的「抽卡」实现，以数量去对冲概率

这种情况下，如果能用好控制出图的三个最关键因素，能让「出图与我们想象的画面一致」概率更高

1.提示词

2.Lora

3.ControlNet

提示词的作用是奠定整个图的大致画面

Lora的作用是让图片主体符合我们的需求

ControNet的作用是精细化控制整体图片的元素——主体、背景、风格、形式等

提示词的用法我在SD的教程里讲过，这个更多的是需要平时的积累，用AB测试去知道每个词对图片产生的影响，从而养成提示词思维

Lora模型的训练教程我也写了，在这个文章里

而我们这篇文章主要讲的是ControlNet的用法，把15种模型都给你演示一遍，让你知道每一种模型有什么用，应该怎么用，从而真正掌握ControlNet

ControlNet就是你提供一张图片，然后选择一种采集方式，去生成一张新的图片

比如你提供一个图片

可以选择采集图片中人物的骨架，从而在新的图片中生成出一样姿势的人

可以选择采集图片中画面的线稿，从而在新的图片中生成一样线稿的画面

可以选择采集图片中已有的风格，从而在新的图片中生成一样风格的画面

用的时候不必拘束于哪一种模型更好，更重要的是你脑海里想要什么样的画面

多去尝试，也可以结合其他模型一起用，最终把图片变成你想要的画面就可以了

# 三、ControlNet安装

在正式学习controlnet之前，我们要先更新版本

不然有些功能没法正常使用

安装新版ControlNet分为三个步骤：

*   下载ControlNet

*   更新ControlNet

*   安装预处理器

*   安装模型

## 1.下载ControlNet

一般我们通过整合包安装的Stable Diffusion都已经装了有ControlNet这个插件

我们可以看看自己的SD最下面有没有ControlNet，如果没有的话要先下载插件

如果你已经有插件就直接看下一步更新ControlNet

![](img/cfd011510534f2767806805066631088.png)

下载ControlNet方法：

①点击状态栏里的“扩展”

②点击“加载扩展列表”按钮

③在搜索框里输入“controlnet”

④找到controlnet，点击右边的安装按钮

因为我已经下载好了，所以搜索出来没有controlnet

![](img/90014088e7c1aafb721b09e7ea5089c2.png)

接下来等安装完成就可以啦

## 2.更新ControlNet

①打开SD的启动界面，点击最左边的“版本管理”

②点击“扩展”

③找到controlnet，点击右边的“更新”按钮

![](img/4b50849bf8f76d84300a307f62c688c8.png)

## 3.下载预处理器

预处理器的模型放在了网盘（网盘链接在文章最后）

下载网盘里的《1.预处理器》文件夹

里面有一个“downloads”文件夹

把整个文件夹复制到SD的文件夹里面

具体位置：SD文件 > extensions > sd-webui-controlnet > annotator

![](img/0ccc686c24c37a40208bb72fc90c7c8c.png)

## 4.下载模型

下载网盘里的《2.模型》文件夹

里面有14个模型，把这些模型复制到SD文件夹里

具体位置：SD文件 > models > ControlNet

![](img/c2986b5d82593a2f3a86d4389c6eb787.png)

到这里我们的ControlNet就已经更新好啦

# 四、具体操作步骤

Controlnet里面总共有14个模型，理论上来说就可以有14种用法

甚至可以两个或者多个Controlnet一起用，这样就有更多的玩法了

但不管怎样，它们的具体操作步骤都是差不多的

接下来我们先讲解controlnet的统一操作方法

再讲解controlnet的每一个模型的功能

我们就用最常用的“控制姿势”作为例子

详细的讲解Controlnet的具体操作步骤：

*   1.基础设置

*   2.controlnet的使用

现在我们需要让黑色衣服的小姐姐摆出白色衣服小姐姐的动作,得到最右边的照片

![](img/659a7cff22086a0a9530f593f32502fe.png)

## 1.基础设置

首先我们先正常的生成出来一张满意的照片

这里的基础设置就是：

选大模型、写关键词、用Lora、参数设置等等

这一步的内容在Stable Diffusion的教程里面都有详细讲到，这里就不再具体去拆解了

如果忘记了或者有不懂的可以看回这篇文章

![](img/843ef35a293f5e6f3a857796302f8ca3.png)

这时候直接点击生成就得到了一张比较满意的照片

![](img/72fe271683c2fea079c164d3fb5d016f.png)

为了等一下加上controlnet控制姿势也能生成出来一样的照片，我们要固定照片的随机数种子

![](img/bf6dec6079bd52cc504285fc54828891.png)

接下来我们就在controlnet里面控制小姐姐的姿势

## 2.controlnet的使用

controlnet的使用方法就只有两步

*   上传图片

*   选模型

滑到SD最下面打开controlnet的面板

![](img/e3ba16eae845aab38de1a13a3eaeb44a.png)

上传一张人物姿势的照片

下面的“启用”按钮一定要打开，其他按钮可以按照我的选

电脑显存比较低还可以打开“低显存模式”，但是照片生成速度会比较慢

![](img/7539a8b0854e6c96195c067a132219af.png)

看到控制类型有很多个选项，这个其实就是快捷键

选中“OpenPose”

就会自动帮我们加载预处理器和模型

![](img/3e1fac9e55fea4ea516fa60903b93588.png)

点开 预处理器 的选项卡，里面的所有预处理器都是去识别照片姿势的的，只是识别的东西有多有少

我们这里就用最普通的“openpose”

其他的会在后面细讲

![](img/b8e6d16c5f4a8abc032b300e8e9ac18c.png)

点击爆炸按钮 “💥” 就可以在图片右边看到预处理之后的人物姿势线条

![](img/fcc5a1ef1d036b54a62cb4c6a579a5ab.png)

最后点击生成，小姐姐就摆出我们指定的姿势了

![](img/2627957d02c93bcf0aa3a023ccb6d643.png)

![](img/6e9317336774e83e9f9e821f41a4e9d2.png)

controlnet的不同功能的实现其实就是上传不一样的照片，然后选用不一样的预处理器和模型

一般情况下，预处理器和模型名字一样，是配套使用的

controlnet是辅助我们生成想要的照片的一个工具

我们的大模型和关键词也非常关键

要换照片风格一定要记得换大模型

一般情况下二次元图片用anything

真实照片可以用chilloutmix

接下来我们就看一下每一种预处理器和模型都有什么用

# 五、姿势约束

这一节讲的是openpose模型，主要控制生成照片人物的姿势

这里的姿势有身体姿势、表情、手指形态三个

可以只控制某一个或者两个，也可以三个一起控制

身体姿势

身体姿势+脸部表情

只有脸部表情

身体姿势+手指+表情

身体姿势+手指

![](img/840136cf012201d2d37a8ad6e3b55b45.png)

## 1.控制身体姿势

一般情况下，在SD里面生成一张照片，照片人物的动作都是随机的

但controlnet可以让生成出来的人物摆出任何你想要的姿势

![](img/99dcba4efcfb30c2e695a5d70a4345a8.png)

![](img/f99f9682fad1e2e1bb4448ec871272f9.png)

首先我们正常设置大模型和关键词

然后打开controlnet，上传自己想要生成的姿势照片

controlnet的模型选择：

预处理器：openpose 模型：openpose

![](img/7a32dcacdf34b7585a1acb07b03c782f.png)

点击预处理的爆炸按钮就可以看到，模特的姿势被提取成了一个火柴人

里面的小圆点就是人体的重要关节节点

![](img/bee775a3f45dde292abb35260b340663.png)

看看生成出来的照片，模特的姿势就几乎完全复刻出来了

![](img/53bdd5b2416fbd9cbbb045e64f27c617.png)

## 2.控制人物姿势和手指

除了识别人物整体的姿势以外，还可以识别手指的骨骼

这样在一定程度下就可以避免生成多手指或者缺少手指的照片

![](img/085e40f64170acd9a09cd7ba8944cb91.png)

![](img/5bfec7f19d024be241d2e78e66780bd4.png)

具体的操作跟前面是一样的

只是预处理器的选择不同

controlnet的模型选择：

预处理器：openpose_hand 模型：openpose

![](img/ddaef8203c1b900b3ee145b88a7f3cc5.png)

看看SD预处理之后的火柴人，在人体整体姿势的基础上，还多了线条和节点表示手指

![](img/9f2ccc37eeaa361ca744a8ceec08995f.png)

## 3.控制人物表情

openpose除了控制人物的姿势，还可以控制人物的表情

但是用controlnet复刻人物表情比较适合放特写的大头照

这样识别出来的五官才会更加精确

相对应的也只能生成出来大头照

![](img/65d201d55e87099af3d25e4dd3e0f1a6.png)

![](img/f271883d48fb256445e78a166e8d55ef.png)

这里我们又换了一个预处理器

controlnet的模型选择：

预处理器：openpose_faceonly 模型：openpose

![](img/38e9bf23c0dfe71c11924f7f12cb69ae.png)

预处理之后就是把模特的脸型五官用点描出来

![](img/a3503ea5f037adc49319c5f1a43f68ff.png)

看看生成出来的照片，脸型和五官在一定程度上都还原了

但是，如果你生成的照片用了Lora

再用controlnet控制表情可能会导致生成出来的照片跟Lora的人不太像

因为生成出来的照片的人物五官和脸型都被controlnet影响了

![](img/8b7c15bb00e405a1d9cf297f13caed07.png)

## 4.全方面控制人物姿势

这里我们是把人物的整体姿势、手指、表情都复刻了

![](img/c4579dae024a0c3aeace3db75f90cda0.png)

![](img/34ff8c20222efcb11818fe55dfdc439c.png)

controlnet的模型选择：

预处理器：openpose_full 模型：openpose

![](img/e5f1d466aa8aedefe36aee590cffc4e6.png)

看看处理后的照片就会有我们上面说到的所有东西

![](img/2b2c1f28299e1fbea56569e0e4141885.png)

## 5.自由编辑火柴人

有时候预处理器处理出来的火柴人可能会不太准确

又或者我们需要更加细致的去调节

这时候我们可以再安装一个插件，这样我们就可以自己去调节预处理之后的火柴人

![](img/83d0b107643f71206fb7bbb6ca9055a5.png)

### 01.安装插件的方法：

①在“扩展”里点击“可下载”页面

②点击“加载扩展列表”

③在搜索框里输入“openpose”

④安装“sd-webui-openpose-editor”

![](img/66e16492e84946fb6a66e81cf004899b.png)

⑤点击“已安装”页面

⑥点击“应用更改并重载前端”按钮

![](img/e262ffe3d2420c8db7afa2e79145b1f5.png)

这样插件就安装好啦！

### 02.插件的使用方法

接着我们回到controlnet里面

点击预处理后的图像旁边的“编辑”按钮，就可以自行去编辑火柴人的节点

如果打开编辑按钮是空白的，那就先点击一下预处理之后的图片，再去编辑

![](img/6a0c3bb376c4496a5f5d1ed86a76b46b.png)

把鼠标放到圆形节点上面，就可以调整位置

调整好了之后，点击左上角的“发送姿势到controlnet”就可以啦

![](img/946d323cd1f90f978eb536c5d288893d.png)

这样通过自己的调节，把腿的节点拉长，就可以生成一个大长腿美女了

![](img/500485a4baa48c96f0e909b4f015682c.png)

![](img/831e45f34af1be295c112409f03c13ec.png)

## 6.小结

识别人体姿势有五个预处理器，在这里有一些我自己选预处理器的小技巧

在日常使用中，如果原图的手指骨骼比较清晰，可以用识别到手指的预处理器

如果识别出来的手指线条比较乱，自己调整也没调整好，那就只识别身体姿势

不然生成出来的照片手指反而更乱了

控制表情的最好用在生成近景特写图片，这样识别出来的才比较准确

![](img/bd18b3318570393c79a205d679083633.png)

# 六、线条约束

这一节会讲到lineart、canny、softedge、scribble、mlsd五种模型

它们都是用来提取画面的线稿，再用线稿生成新的照片

![](img/0d5ab17e815abcc11013c2ef633df362.png)

## 1.lineart

lineart是一个专门提取线稿的模型，可以针对不同类型的图片进行不同的处理

点击选择“Lineart”，预处理器和模型就会自动切换

![](img/73d6cfe6de807878f2c5bb6e8907f483.png)

点开预处理器

里面的各种模型可以识别不同图片的线稿

动漫：lineart_anime 或 lineart_anime_denoise

素描:lineart_coarse

写实：lineart_realistic

黑白线稿：lineart_standard

![](img/abe667ce8d0fce21d9b388a80c7d8d09.png)

### 01.动漫照片

提取动漫的线稿，再重新上色

![](img/0b4c8f3b3e8a57e56e170930e92549c5.png)

![](img/5c8e6187511fdf515b1344789d377400.png)

首先处理动漫照片记得要换二次元的大模型

然后关键词可以写一些质量词，然后描述一下照片里面有什么东西

另外需要注意的是，图片的分辨率大小要设置的和原先的比例一样

不然照片会自动裁剪放大

controlnet的模型选择：

预处理器：lineart_anime 或 lineart_anime_denoise 模型：lineart

![](img/3f9c6de4521c9730cc0a460abbd99baf.png)

可以看一下两个预处理器出来的效果，选一个自己比较喜欢的就可以

lineart_anime

![](img/709fb537b170738e2dad01df5247b8f7.png)

![](img/9c8b453a7c58fe9abb7d56d64fd36378.png)

lineart_anime_denoise

![](img/9c0e67e1cfa3fc03363428e13a186165.png)

![](img/716f487d021ff60ba5c1debe1f9341d4.png)

### 02.素描照片

![](img/db25b505505f09aa6a842e3f1143c692.png)

![](img/d14af5162e9ce180fa0dfbe57b735a5f.png)

controlnet的模型选择：

预处理器：lineart_coarse 模型：lineart

![](img/2d2e08a5eb26e01eeb2dfc65eb0f170d.png)

### 03.写实照片

可以上传自己的照片，提取出线稿，然后生成自己的二次元头像

![](img/d304a68d00f15ab9d5b1e65202a79d3c.png)

![](img/465fcd404d237ad1db9ea2c545bcfc63.png)

要生成二次元照片，一定要先换成合适的大模型

controlnet的模型选择：

预处理器：lineart_realistic 模型：lineart

因为真人照片换成二次元在五官比例上会不太匹配

这时候我们就要适当把controlnet的权重降低

![](img/ce684d25f8e26f87ed52682685c190f3.png)

还可以将真实的照片转换成真实的照片，生成一个长的很像的人

![](img/965416fb1cbf599d9fcc209bb2d14a5e.png)

![](img/dee12ef11675a7a9dd477183dce90471.png)

### 04.黑白线稿

![](img/fa3f866b989a198b83e36b4036da65b9.png)

![](img/d87936da5af2b193c758bfce6a2c4ef0.png)

![](img/53430ffd90f63e69a203b80e380f5685.png)

controlnet的模型选择：

预处理器：lineart_standard 模型：lineart

![](img/6a1dec807e250c8f5af2166d11516819.png)

## 2.canny

canny可以识别到画面的最多的线条，这样就可以最大程度的还原照片

但是比较适合二次元照片

![](img/d25928276036dc7704e579f1bcb462ec.png)

![](img/fcc7f85bfc1d2f03644505b0642098e7.png)

controlnet的模型选择：

预处理器：canny 模型：canny

![](img/eb346d68bd62b17a3ea67b1f971f89ab.png)

![](img/b3dbfb8644f89428d50f7efea3480038.png)

![](img/dfa874248c63859141ae62128276180e.png)

## 3.softedge

softedge只能识别图片大概的轮廓细节，线条比较柔和，这样给SD发挥的空间就比较大

![](img/d64629762c77a7a93379eaf2d8e4febf.png)

![](img/b69450153a80a294092b524d962a0389.png)

controlnet的模型选择：

预处理器：softedge_pidient 模型：softedge

![](img/a1c6394ab81a5e219c10cc73a4cb3889.png)

![](img/d45c7ae96be0bb22c10098b48fd49fb7.png)

![](img/29489a5e18de05e85241ede819eab997.png)

## 4.mlsd

这个模型只能识别直线，所以只适合拿来做房子的设计

![](img/b6472127c093a0a696d443e6bd26a2e5.png)

![](img/8fb109f6e2184b31c77fbd6f2dc1783f.png)

controlnet的模型选择：

预处理器：mlsd 模型：mlsd

![](img/e3e83ac901924d2817842147309c32d0.png)

看看预处理出来的图，都只有直线

绿色植物和瓶子这些有弧度的线条都会被忽略掉

![](img/44b886b0e7f37d3bc91dc0f9d0b4193c.png)

## 5.scribble

这一个功能和图生图的涂鸦功能一样

可以将自己随便画的东西放进去，通过输入关键词得到有着一样线条的照片

![](img/70d493faee2f46c0cb7f6488f1d08b4f.png)

![](img/99b830cb766045db31fa47f0c239001a.png)

controlnet的模型选择：

预处理器：invert 模型：scribble

![](img/9a946a366dd59ae2762c683a1864c2fa.png)

## 6.小结

识别线稿的模型有很多，如果你不知道什么情况下用哪个好，可以参考一下我的选择

1.想最大程度还原照片：canny

2.只想控制构图，给SD更多可以变化的地方：softedge

3.真人、素描等照片：lineart

4.建筑物装修：mlsd

# 七、空间深度约束——depth

能够很好的复刻房子线条，而且物品的距离镜头的前后顺序比较清晰

![](img/8a933fbf4274f6cd708ef28ae1865826.png)

![](img/df07530340edcdf938bcd79045c0a0ab.png)

controlnet的模型选择：

预处理器：depth_leres++ 模型：depth

![](img/6a66799f337c7e3bfb048d85859f3aea.png)

# 八、物品种类约束——seg

识别图片不一样的东西，就用不同的颜色表示

![](img/630d2fe29b19d1c8e25f2be1907e9594.png)

![](img/6eb37f709030d514b5eba27137a7ea59.png)

controlnet的模型选择：

预处理器：seg_ofade20k 模型：seg

![](img/e40bb1f036d5c9187e6d3c1e5c7d61a0.png)

可以把seg色块图下载下来，自己到ps或者其他修图软件改照片物体的颜色

这样SD就会根据颜色生成出来特定的某样东西

网盘链接里有一份文档，可以看到不同的颜色代表什么物品

![](img/b69a836a9267afecb33108be6b1db9ef.png)

![](img/b8a0948826be2b58b54573882c7e0923.png)

## 小结

看到这里建筑物装修已经有三种模型可以处理了

1.只还原整体的结构：mlsd

2.还原物品的先后关系：depth

3.比较好的还原原图有的物品，想自己后期编辑色块，改变室内装修结构：seg

depth和seg除了用在建筑上，还可以用在人物照片

# 九、风格约束

这一节会讲到shuffle、reference、normal、t2ia四个模型

![](img/fa24d16bbeea70167781f343a83ee6e7.png)

## 1.shuffle

将其他图片的画风转移到自己的照片上

下面第一张是原图，其他三张分别是由水墨画、油画、赛博朋克风格的图片转移过来的画风

![](img/2510b7e98229b82b1fd08a8638e7fe43.png)

![](img/8a307d8f59d8a87518f7556f288892d0.png)

![](img/b6f96daa85aac4d79ff23b832d22ea18.png)

![](img/c9b0bf0f6c810f9203f58c5c31edee6c.png)

首先先用大模型和关键词生成一张自己喜欢的图片

固定随机数种子

然后打开controlnet将别的照片画风转移到自己的照片

controlnet的模型选择：

预处理器：shuffle 模型：shuffle

用shuffle可能会影响自己原图的形状，可以稍微调整一下“引导介入时机”的参数

设置在0.2~0.3之间就差不多

先生成出来大体的形状再去改变画风

或者用两个controlnet：一个固定线稿，一个影响画风

![](img/f578b0c996056ab8ca149adf0e84b490.png)

## 2.reference

可以很好的还原原图的角色

### 01.让照片动起来

让坐着的小狗跑起来

![](img/9d761b62078562f0913695936e1888cb.png)

![](img/00be00131cd401f32083039d969e017b.png)

选择写实的大模型

然后在关键词里面输入：一只狗在草地上快乐地奔跑

![](img/3aaaa46c06612bb21de3a921044522f0.png)

controlnet的模型选择：

预处理器：reference 不用模型

![](img/bc1540731924a0a2919fdfad97f537c9.png)

### 02.还原角色

给SD一张人物角色图，它会根据人物的五官、发型还原这个人物

![](img/4b46d07fc15b469852158013dbf2eff4.png)

![](img/48baa5eb7293a1bb81dbd08a0de14bf5.png)

具体操作方法和上面是一样的

关键词还可以加上情绪的描述，或者不一样的服装发型

![](img/0dbc76b947d5b0cc6422304db1f1c969.png)

![](img/fd3de7b7b48bd100ae7e7820d7ad9c99.png)

## 3.Normal

这个模型可以参考原图的明暗关系，并且还原原图的姿势

![](img/9f0af40afe23cbf6fce6c1970c556055.png)

![](img/e745dcd5548bf4947ed06b9e475ca4e1.png)

controlnet的模型选择：

预处理器：normal_bae 模型：normalbae

![](img/7c495244e3a0b70cd5229c336cf3f35e.png)

## 4.t2ia

t2ia这个模型比较特殊，不同的预处理器要用到不同的模型

它的主要功能有3个

1.将原图的颜色模糊成马赛克再重新生成图片

2.提取素描的线稿，生成真人照片（这个不好用，直接用lineart就行）

3.参考原图风格，生成相似风格的照片

参考原图的颜色，将原图模糊成马赛克，再生成图片

![](img/309efe6350723e2ec7d6a4a8cb8e39a8.png)

![](img/895c4dc2d5e7072339e359f25e011eb2.png)

controlnet的模型选择：

预处理器：t2ia_color_grid 模型：t2iadapter_color

![](img/c3eb6af65acd8b4afe070d677170ed24.png)

# 十、重绘——inpaint

和图生图里的局部重绘差不多，但是inpaint可以将重绘的地方跟原图融合的更好一点

## 1.消除图片信息

![](img/4ba6665e805ec4f38af6f75cc6196ab3.png)

![](img/b55c138af9ac16e5102be1b222c9fa1b.png)

![](img/af773b59c4f83d2eee430c51e7ef0a1b.png)

关键词填写照片背景的描述词

controlnet的模型选择：

预处理器：inpaint_global_harmonious 模型：inpaint

inpaint_global_harmonious预处理器是整张图进行重绘

重绘之后整体融合比较好，但是重绘之后的图片色调会改变

inpaint_only只重绘涂黑的地方

为了重绘之后的图片更像原图，可以把控制权重拉满

![](img/47d6c248cdc30417604d3221e02c40a3.png)

可以看看在图生图局部重绘出来的效果，是不如inpaint的

这张图是我跑了十几张图之后选的比较好的一张

![](img/878cdb80e36266bd6b68f03e0b06a310.png)

## 2.给人物换衣服

![](img/5df58c9313f252e170b262f533da41c6.png)

![](img/d621786130d4dfe6f7c19dcd68ddf0bc.png)

操作方法和上面一样，只是关键词的描述不一样

# 十一、特效——ip2p

给照片加特效

这个功能目前来说没有太多的实际用处，只能拿来玩一下

比如让房子变成冬天、让房子着火

![](img/ce9e157fb590936dd6f844aec476d064.png)

![](img/3793c2cb3307419c1995f711e665bd91.png)

![](img/ab31f6dc7793894321c99b99551b6a85.png)

这里需要输入的关键词比较特殊

需要在关键词里面输入：make it.... （让它变成...）

比如让它变成冬天，就输入：make it winter

controlnet的模型选择：

预处理器：无 模型：ip2p

![](img/a716908b95fd13de9fa83bedf4bb5169.png)

# 十二、加照片细节——tile

tile模型的玩法有很多

## 1.恢复画质

![](img/16e956651dd6202c8dea3fbe1cad5653.png)

![](img/5817ecce1710a68654a679b6bea62837.png)

controlnet的模型选择：

预处理器：tile_resample 模型：tile

![](img/3ac328b4eb11bcb22b41e793e261d7af.png)

但是这个恢复画质的方法可能不太适合真人

因为tile模型的工作原理是先忽略掉照片的一些细节，再加上一些细节

这些SD自己加上去的细节可能会导致生成出来的照片不像原图

![](img/dd7ee477c365752da808dcc360089394.png)

![](img/dd4eed85d0d11a4401385b9f057b2628.png)

## 2.涂鸦

将自己画的图给SD加工

![](img/b9e42b039940872f743ab00dcf006da6.png)

![](img/5f4a0cf02adf9c90b2aee4585568906d.png)

## 3.真人变动漫

![](img/773df3995c155e3924f0877717af7d48.png)

![](img/1624a9ed26f86ef2b6060d28f21d2f80.png)

## 4.动漫变真人

![](img/739bcdf17b0d1725224982a88e4d1576.png)

![](img/1ce75726713994fbce60bfe25835a51a.png)

![](img/1715b61bc09584d2e69d1f2ae38c8114.png)

![](img/42cc619bdf6e93fe4e92ec67c3a35c7a.png)

# 十七、结尾

这是整个controlnet的思维导图

希望可以帮助到大家更好的理清controlnet的功能用处

目前用SD很多时候还是在“抽卡”

只是controlnet可以帮助我们提高成功的概率

并不是说用上controlnet就一定能出来自己满意的照片

模型关键词还有一些参数一样要反复的调整

但随着AI技术的不断迭代升级，未来还会有新的模型、更新的技术

最终AI绘画或许就可以实现——让出的图与我们脑海里想象的画面一致

如果你对AI感兴趣的话，可以关注我的公众号：吴东子AI，也欢迎分享给你身边想学AI技术的朋友

里面有我之前发过的所有文章，之后也会持续给大家更新实用的AI干货教程

我是吴东子，用奶奶都能听懂的方式，分享可以落地实操的干货，我们下篇文章再见！

网盘链接：https://pan.baidu.com/s/1EFXv7dgWu2vIH86gwSpfkQ?pwd=4dxj

提取码：4dxj

吴东子AI账号简介：https://ry5hwpuf7b.feishu.cn/wiki/space/7283841978071072772?ccm_open_type=lark_wiki_spaceLink