# CentOS系统安装docker 从0到1

> 来源：[https://wq47vbhmbi1.feishu.cn/docx/XnlLd77nYoZbFZxQADscBo3Jnsh](https://wq47vbhmbi1.feishu.cn/docx/XnlLd77nYoZbFZxQADscBo3Jnsh)

# 准备一台centos系统

首先我们在阿里云、腾讯云或其他vps厂商购买一台centos系统的vps，我这里买香港地区，因为香港地区的网络可以直接fq，如果搭建一些应用网站不需要备案就能直接访问测试。

![](img/ab2fdc03076f91e821a64c7c4d356944.png)

成功购买之后，重置密码。这个界面可以看到你vps服务器的公网IP地址，后面需要用到这个去链接

![](img/e5e36fe0e81fd4032d9bb538f30cf1fe.png)

# 放通防火墙

我们把vps的防火墙全部放通，以便于我们后期做测试。进入服务器的控制界面

![](img/3acc0bc78bf7b0721072aef26a4a5355.png)

点击“防火墙”----“添加规则”

![](img/621eae89d0dcfc5a5cbdbc0d2bbf2862.png)

![](img/dc075a8a32800996b75edef49ce402db.png)

然后使用我们ssh链接工具，链接这个vps

# 链接登录vps

使用Xshell，Xftp这俩种工具都安装好，链接vps我们就使用Xshell进行链接

![](img/e69179c7e683b6cc2930a362377dcdd3.png)

打开Xshell，点击右上角链接

![](img/2a8cd5b4443ecf8067c442faf0a9a0b9.png)

在弹出的界面，填写你服务器的ip地址和ssh端口。

![](img/3e755ecc5b3742fd7489993d8af75764.png)

![](img/d2177889d88615d24c77bc27d0064861.png)

然后点击链接，输入服务器的用户名root和你刚刚重置的密码链接即可，

[root@iZj6c2jrfa4av3bcbgeyx9Z ~]# 出现大概这个样子就说明已经链接成功了

![](img/8ba495225c072e656675c269c64349b0.png)

# 安装Docker

```
curl -fsSL https://get.docker.com -o get-docker.sh

sh get-docker.sh
```

俩行代码一次复制到咱们的vps里面，就开始安装docker了，安装需要一点时间，等待后台自动安装即可

![](img/71a87a5cd38ea55a9904757546bee71e.png)

代码跑完之后出现这个状态，咱们就安装完成了

![](img/3d8c8ad99f6d8605b8bd87ea66663859.png)

```
docker --version
```

运行docker --version查看一下docker版本，看看有没有安装成功，显示出版本，说明我们安装成功

![](img/cb0054c23e082c61e8e9a995cb88a74a.png)

# 设置docker

```
#设置docker服务开机自启动
systemctl enable docker

#启动docker容器
systemctl start docker

#查看docker是否运行
systemctl status docker
```

![](img/7ade45c6590a83ea464ea7acf5cce81e.png)

docker的active状态显示running，就说明咱们已经成功安装好docker了。

好了朋友们，下期内容，使用Docker里面搭建chatgpt