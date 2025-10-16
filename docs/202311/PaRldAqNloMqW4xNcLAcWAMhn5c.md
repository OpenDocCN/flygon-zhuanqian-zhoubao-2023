# 自动监控+加图表分析 对标数据

> 来源：[https://w0kp7t5wqc.feishu.cn/docx/PaRldAqNloMqW4xNcLAcWAMhn5c](https://w0kp7t5wqc.feishu.cn/docx/PaRldAqNloMqW4xNcLAcWAMhn5c)

做抖音有一年了 抖音对标的帐号不说一百 至少也有大几十个了

所以呢经常就在找各种方法 想把对标的数据第一时间统计下来 对标的作品几点发的 什么时候爆的 今天100个或者更多的对标中谁的视频爆了 我能不能第一时间跟上

有没有什么办法能够帮我定时去帮我扒对标的点赞 （比如定时1小时帮我去记录一下）

然后记录下来的数据还能做到EXCEL一样的图表

就比如像下面的表格 到了这里相信会用EXCEL 图表的应该就懂了

![](img/a5f60c2ee38cd0c70370691c391dff66.png)

![](img/f316a9f0b3ec1b0b23fc9b9e1c3e946a.png)

![](img/8b37a584b3994ab2ce470fc18482346a.png)

好了下面是我的一个流程图

工具 ：

影刀RPA +飞书的多维表格 （这两个全是免费的）

# 1 用影刀写一个脚本 让机器人定时固定的时间 或者每隔多少时间去扒一下对标

影刀的脚本地址：（明天 等待分离脚本）影刀的脚本 https://api.winrobot360.com/redirect/robot/share?inviteKey=12838d2e26f47359（密码2023）

1先在C盘下 建个 【抖音配置文件.xlsx】

![](img/ab03d22947c290739de947601b4ede8c.png)

2在excel下建

![](img/cc5d35af66bbcc1ebce0f075357b8557.png)

3配置对标主页(一行一个对标 不要有空行 因为我没有空行所以不知道中间空了会怎么样)

![](img/941424da2b7eba0d8a0edf0660f4ef19.png)

4【记录] 页是数据的一个本地备份 这里也是自动的不用管 但是要把这个页面建好

5影刀的一个设置页面 其它的就没有

https://ydrpa.yuque.com/org-wiki-ydrpa-xtutvv/ga4dm6/ir3mh6orhy4ib7zf（多维表格ID 示列）

![](img/f4ba95cf920c7686c234b225492c56c4.png)

6注意 注意 注意 注意 注意 （因为影刀的原因系统不一样 会有不兼容的情况 这是我的系统版本 结尾贴上影刀的代码

![](img/d0fcd64451d712cb354f775d874f4e3e.png)

）

如果影运行出现 下图报错问题第一次把这个C列有数据的地方加个时间 （不能是未来的时间不然就不抓取了）

![](img/4711a29018b7a5754ffb25d4eca0a55c.png)

![](img/56b729cb47f96bfc8d026851e1dcce73.png)

# 2 让影刀把每一条数据通过飞书的API接口

![](img/8b230830dfdb604de1f8c248bb6ccf06.png)

把数据传到多维表格

![](img/467b73a4053e4fb46ccd86edffd7f9c1.png)

https://open.feishu.cn/app/

1对接前需要去飞书开发平台去开放权限

![](img/8e504b9f7e40fa59b96d4bf631aff2b1.png)

2点新建的应用

![](img/4a3f5f4a7b0180ba7ea8eabe2b5d1c03.png)

保管好自己的ID 后面填写到影刀当中

3开通记录的权限

![](img/b702d0bf1ad01049e15fd9283de7e9c0.png)

4发布应用版本

![](img/8c22bacba431cd6f8eef68d0a8ff2b0a.png)

5去自己的飞书建个多维表格

![](img/ae755159cadd3b9957355bdbaf95a8a3.png)

6把这个多维表格 添加到刚才的应用里去

![](img/2bf4452fc65eb6961bb8e94704b27e50.png)

![](img/3e51ee8deb358b2dccf993491e826ee1.png)

![](img/cd78d27591f319a4e0cbf8d87a36c15b.png)

并且给到编辑的权限

7 等影刀机器人自动上传数据 有数据了 你就可以去飞书的仪表盘添图表了

不会图表的 要自行去补一下EXCEL了

![](img/d2a2bddc9550af92a4ca2ae4867c1b71.png)

8去多维表格建表的时候注意

![](img/54607ec1d3e64fab56db1ddcf785939d.png)

![](img/977ae1e31bc19184edf32dac32f9d6f1.png)

![](img/1ffcc8b74e97065fd8e9390efe6c4cee.png)

![](img/9af02135648df901be2a72de1d9cf401.png)

![](img/9766a9217ef052eb0a98f960ac1c68be.png)

其它的全文本格式

9自由发挥查你想看的数据了 下面是我自己用的着的一个数字仪表盘，每个数字都可以单击 都能点出明细表

![](img/995ed6efe33c9105823ab42b3877199b.png)

![](img/86ac5d9db593d34bd8c114b666f04104.png)

就比如上面 这样对标的数据是不是一目了然 非常的安逸

* * *

# 3影刀代码

## 主流程代码

![](img/225e7260d1801216359b5fc90d10aa97.png)

![](img/5e3c2b27738bb524b795dccfbd528a16.png)

![](img/1db65a27b5be45a622aa2163988a7e08.png)

![](img/e746a88cff096ed73cd7bdbfdda99c55.png)

![](img/7cf72fcf966bdcd671da2b8b9508e85d.png)

![](img/050011d1938dced9c1932b6f70c82743.png)

## 2监控流程代码

![](img/5c43062bbad2f0546c9603983a93c8e2.png)

![](img/8a02cbca8863c702c5d1809a41e72aee.png)

![](img/ffdc296464865cf7d63c4d4373c3b51d.png)

## 3 检查微信存在流程

![](img/fb9705d6ffd85581287441e153ef9e14.png)

## 4配置流程

![](img/36b8f5f423285fb82a8677af7c12f69a.png)

![](img/49d2e2fdaf24d0907935a49f60b8e4df.png)

![](img/3e053df0851e85ecfbe3d515c193ddec.png)

## 5筛选流程

![](img/7981eeed3e11ab9cf86726919f3b4ed1.png)

![](img/d93aabaaf9bb6d4f0cd04dc121d78e99.png)

![](img/c9016cefe815c2ae794878e6ae68650c.png)

![](img/c479ed7fc8e8909a98fc895b4b39bf73.png)

![](img/db99c61f5d13755b02a122147e146d62.png)

![](img/448086155411a7a51841aef7292b3115.png)

![](img/26676bd22341f5210f4a195d3934fad1.png)

## 6微信发送流程

![](img/3dc61f265a50d5043f32ee424ba78695.png)

![](img/7d285644223c1cb39e194e6e20efa93e.png)

到此 所有结束 原来的工作原理是发送的微信的 后来发现飞书比微信好用 所以微信部分的有会写代码的可以自行删减一下

第一次分享 排版不好将就着看吧