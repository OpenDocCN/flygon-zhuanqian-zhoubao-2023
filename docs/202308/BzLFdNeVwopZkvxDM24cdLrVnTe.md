# GitHub Copilot教程

> 来源：[https://sif8f6uboze.feishu.cn/docx/BzLFdNeVwopZkvxDM24cdLrVnTe](https://sif8f6uboze.feishu.cn/docx/BzLFdNeVwopZkvxDM24cdLrVnTe)

# Copilot是什么?

Copilot是github为开发者提供的AI辅助编程工具，可以帮助开发者在编写代码时提供代码建议。

*   官网地址：https://github.com/features/copilot

*   官方文档：https://docs.github.com/copilot

包括一些核心的概念：

*   Transformer

*   大规模预训练模型

*   代码片段

*   代码建议

*   Prompt Engineering

# Copilot可以提供什么价值?

Copilot确实是一款强大的工具，它能帮助开发者提升编程效率、降低编程的门槛和成本。

*   ⚡提高开发效率：Copilot能帮助开发者快速编写各类业务代码，包括增删改查的操作和单元测试等。

*   🔑降低编程门槛：对于新的编程语言、框架、库，Copilot能帮助开发者快速理解并编写代码，快速实现原型。

*   💰降低编程成本：Copilot对于一些机械性、繁琐的任务，如SQL、正则表达式（Regex）、Cron等任务有着良好的处理能力，可以大大减少这些任务的编程成本。

# Copilot的基本原理

Copilot的核心是一个基于GPT-3的大规模预训练模型，它可以通过大量的代码片段进行训练，从而学习到代码的语法、语义、结构等信息，然后在编写代码时，根据上下文，生成代码片段，从而提供代码建议。

*   代码片段

*   Copilot的训练数据是大量的代码片段，包括github上的开源代码、Stack Overflow上的代码片段等。

*   这些代码片段包含了大量的语法、语义、结构等信息。

*   Copilot可以通过这些代码片段进行训练，从而学习到代码的语法、语义、结构等信息。

*   Prompt Engineering：

*   Prompt Engineering是指通过一些技巧，将自然语言转换为模型可以理解的格式，从而提高模型的准确率。

*   例如，将for循环转换为for i in range(10):。

# Copilot的优势和缺陷

🎉 Copilot的优势在于：

*   代码建议准确率高：它能根据输入的代码片段，给出准确的代码补全建议。

*   支持多种语言：包括但不限于Python、Java、JavaScript等。

*   支持多种编辑器：如VS Code等流行的代码编辑器。

*   支持多种操作系统：包括Windows、MacOS和Linux。

⚠️ Copilot的缺陷在于：

*   代码建议不够智能：有时候，它可能不能理解复杂的编程逻辑，给出的建议不尽如人意。

*   代码建议不够全面：对于某些语言或者特定场景，Copilot可能不能给出全面的代码建议。

*   代码建议不够安全：在某些情况下，Copilot可能会生成可能存在安全风险的代码。

# 如何安装Copilot

主要步骤分为如下4步:

1.  申请

1.  申请Copilot chat(可选)

1.  安装插件并配置具体的语言

1.  登陆账号

1.  开始使用

官方入门指南的链接: https://docs.github.com/en/copilot/configuring-github-copilot/configuring-github-copilot-in-your-environment?tool=jetbrains

## 申请

首先申请，并开通 copilot, 地址为：https://github.com/features/copilot，copilot 一个月10美金，第一个月免费，支持国内的信用卡。

这里售卖使用机会也是一个小商机。学生身份目前是免费的。

## 申请 Copilot Chat (可选)

当前案例为个人版，企业版本方式大致一样，最大优势就是不需要等待时间。个人版本一般需要等待半个多月。

开通copilot之后，可以申请 Copilot Chat 的功能，网址为：https://github.com/features/preview ，通过下图中箭头指向的入口申请 Copilot Chat 的功能。

注意, Copilot chat 目前只适用于以下两个软件和版本:

*   最新版Visual Studio Code - Insiders

*   Visual Studio 2022 17.5.1及之后的版本

![](img/30b9ef84bb075668a03cf395fefc2781.png)

一般需要等一个月左右, 申请通过之后，会收到一封标题为You’re now in the GitHub Copilot chat private beta!的邮件，邮件里有安装方法：

![](img/91d17cbf5c569b8071691ac7a3a2b2ac.png)

## 安装

### Visual Studio

1、确保您正在运行Visual Studio 2022 17.5.1或更高版本。如果没有，请更新。

2、搜索并安装扩展程序 GitHub Copilot .

![](img/67d49d449be7a090ebdf0053ebe13a03.png)

点击 Trust Workspace & Install.

![](img/b7e9c51e6cee66fe2dde66e89d41a62d.png)

3、搜索并安装扩展程序 GitHub Copilot Chat .

![](img/e93576a47c624a8f7ee885e92f01b786.png)

4、重新启动软件, 并登陆 GitHub 账号进行授权.

![](img/e87e471776ede6665315963d515a1e9b.png)

![](img/6dcfbd13ca460e9655abf88bc9d6984b.png)

输入 账号/ 密码 进行登陆账号.

![](img/aef121b69c6b76acbea7231cad00319a.png)

![](img/bbad315446a2a10c2601a58f750ec553.png)

点击 Open.

![](img/921b0e3ee994a0f8e0dad44c3f90d3fc.png)

使用本地服务器中验证的方式, 点击 Yes.

![](img/7aedda057e094c673199e28ec7a91e58.png)

跳转到了浏览器, 显示当前已经登陆.

![](img/6673f427860144b554c1706ffb3f60d3.png)

看到设备授权码, 点击 Copy & Continue to GitHub

![](img/ab535c8c3ca742e77c8736d691630a47.png)

在浏览器上输入设备授权码, 并点击 Continue.

![](img/d93dfa2d6da591e5c527923f45bffaac.png)

选择 Authorize Visual-Studio-Code 进行授权设备.

![](img/5edb5bd38b7f94ec291455c264ca66b9.png)

授权成功.

![](img/499ace52756f4777427273512a1f5792.png)

4、检查功能是否有效.

GitHub Copilot 聊天窗口显示在您的视图菜单上. (未申请 GitHub Copilot Chat 功能, 则不会出现聊天菜单)

![](img/729579510d23ed2152743ac3dc467af6.png)

验证在打开代码文件时，代码编辑器中的右键菜单顶部是否出现 Copilot 的按钮。

![](img/ca44561748dae1b12910d62d16397119.png)

### Visual Studio Code - Insiders

1、下载并安装Visual Studio Code - Insiders, 确保您使用的是最新版本!

![](img/1c23e4c5cf705e54ae7f7ba2e6d4e892.png)

2、在 VS Code Insiders 中，搜索并安装 GitHub Copilot 和 GitHub Copilot Chat 插件, 可参考 Visual Studio 章节, 步骤基本一致.

3、成功后, 那么在首页的左侧, 就会看到聊天的菜单了.

![](img/4a5ceba15749182356217d121f0f7a84.png)

### JetBrains IDEs

目前 JetBrains IDEs 系列下, 支持以下软件:

*   IntelliJ IDEA (Ultimate, Community, Educational)

*   Android Studio

*   AppCode

*   CLion

*   Code With Me Guest

*   DataGrip

*   DataSpell

*   GoLand

*   JetBrains Client

*   MPS

*   PhpStorm

*   PyCharm (Professional, Community, Educational)

*   Rider

*   RubyMine

*   WebStorm

本次安装教程, 以 IntelliJ IDEA 为例, 接下来, 我们一起安装下:

1、打开首选项目.

![](img/537100fa7b1ef49d47c572f21bd9e624.png)

2、在插件市场搜索 Copilot, 并安装.

![](img/8f060304eeb6a42e55f464860290ef33.png)

3、安装 GitHub Copilot 后，单击“Restrat IDE”.

![](img/a99d131cd33092d2cc6953ccade7e5be.png)

4、重启后, 单击 GitHub Copilot，然后单击 Login to GitHub。

![](img/0ecd42102e6dfa5d62ba358a2378a103.png)

得到设备授权码.

![](img/903207a5a54ccb050865023e3ab3c2e8.png)

在浏览器上进行验证.

![](img/8f4b21c04e86a6346b97cb91dad8e2c5.png)

![](img/daafa7b032368a94266eb61aab91fd81.png)

设备授权成功.

![](img/0b6f42633b8523a027be60cc01db81a9.png)

# Copilot的初体验

## 根据注释自动生成代码

每写一行注释，Copilot就会给出一个代码建议 (光标所在位置, 则是Copilot给出的代码建议)。如下图所示：

![](img/79f257a6f2bd4ff8cd36a82a28ccf577.png)

按 Tab 则自动补全代码.

![](img/254540c82f3017ed22e9ef81fbea9899.png)

## 根据已输出代码自动补全代码

根据上下文自动补全了代码. 这里需要计算两个日期的相差时间.

![](img/bbe5b7bc94ce3310f51f2b78751d2369.png)

计算出相差的结果为1天.

![](img/60ef910493eac048d28c0f246371986e.png)

# Copilot Chat的初体验

![](img/9ab981717f64b029ab090c024ffada00.png)

发送后, 得到 Copilot 回复的答案.

![](img/04cb9f508817d10e23f95aa5571e9c78.png)

可以选择 Copy 一段代码.

![](img/0eeb64cb6dee5c7eff5c06c117102e5c.png)

将代码插入光标所在位置.

![](img/455903908d0e4f18f1db724c2a903de6.png)

更多操作: 插入到新文件, 或者在控制台运行.

![](img/f58b3bd2bb96cce8cf6a2c8ca25b942d.png)

处理后的代码.

![](img/eaa6a873b6cfc5575217e608be3a6deb.png)

运行成功.

![](img/8b37f3206d86cc0c08898f2c89e51d7d.png)

# 简单功能

## SQL编写

编写完说明文档后（在注释中），简单写一个CREATE字符，Copilot即可提示出完整的建表语句，是不是很nice？

![](img/02146707a41e53948378ba816e8af576.png)

## Regex编写

创建一个regex.js 文件, 编写一个正则表达式的校验工具. 我们来试一下:

*   判断是否为数字

*   判断是否为邮箱地址

![](img/3f1527337b007174dac68fcadc45fa07.png)

## Cron编写

cron脚本的编写也是一个繁琐的工作，我们可以借助Copilot来完成这个工作.

下面的例子中，我们编写了一个cron脚本的说明文档，然后Copilot就提示我们要编写一个cron脚本了。

![](img/a5a928f46c2a7df80c6c00c10d0f7082.png)

# 常规功能

接下来我们会讲解关于开发过程中的常规功能, 如 代码解释、 单元测试编写、修复Bug. 结合实际的应用场景, 这样更能体现 Copilot 到底可以给我们带来什么?

## 了解 Copilot Chat指令

在介绍实际应用场景前, 我们先了解下 Copilot Chat 指令, 通过输入/从可用的命令中选择::

1.  /tests : 为选定的代码生成单元测试.

1.  /fix : 针对所选代码中的问题提出修复建议.

1.  /explain : 解释所选代码的工作原理.

1.  /vscode : 询问关于VS Code的问题.

1.  /help : 关于GitHub Copilot的一般帮助.

## 代码解释

目前 Copilot Chat 功能更加强大, 所以这里以 VS Code 为例.

Copilot的学习能力是很强的，使用Copilot Chat 可以让它结合上下文解释代码的含义.这样,不管是源码, 还是一些注释比较少的业务代码时, 我们再也不慌啦!

我们来看下解释代码最基本的使用步骤:

1.  选中代码.

1.  点击chat菜单.

1.  输入关键词, 以及提示词

![](img/c9d1d4d3342a4b53b4e26826e66ef453.png)

接下来, 我们看看Copilot的回答.

![](img/96f8a66754823b68e0f027e8534e8af8.png)

再找一段Java的源码来试一下, 让它解释下ArrayList.clone() 方法的解释:

![](img/f3d880a6958c188db156248d7819a52f.png)

## 单元测试编写

这里以 VS Code 为例.

我们想要编写单元测试，也可以借助Copilot完成. 下面我们以 JS代码 和 Java代码 作为案例进行演示.

### JS代码

![](img/bc3a6e51c1970ca32fe55d63e48bc772.png)

### Java代码

选择代码, 输入指令生成测试案例, 并说明测试的用例的目的是什么, 即可生成测试代码.

![](img/5880b0a3598e7bfa5f452d58971b3168.png)

## 修复Bug

针对上一步生成的测试用例运行时, 会出现该错误, Exception java.util.ConcurrentModificationException, 那现在我们需要修复这个问题.

选中存在问题的代码, 输出指令和提示词, 并进行调整代码.

![](img/e32dcbc6cc1b5d426ee16cc4e55d193b.png)

修改后的代码运行成功, 未出现任何错误.

# FAQs

## Copilot chat不正常工作?

*   安装/更新 最新的 Visual Studio Code(命令面板:代码:检查更新)。

*   安装/更新最新的GitHub Copilot。

*   您的GitHub账号必须同时具备以下两点:

*   激活订阅(检查您的订阅)

*   接受GitHub Copilot chat内测(加入等待名单, 就是收到了邮件)。

# 总结

目前我为大家介绍了Copilot是什么、可以带来什么价值. 并且如何申请授权、安装以及简单的使用方式.

我们来总结下Copilot最大的几点好处:

*   和编辑器完美融合，使用体验非常 nice，以后再也不用切换了.

*   在读一些源码的时候， /explain真的太强大了吧，以后再也不怕看源码了

*   它还是一个人工智能聊天工具, 基于GPT3.

*   有很复杂的业务逻辑，可以帮助检查代码是否存在Bug, 和改进的空间. 比如询问：“这段代码有什么改进的地方吗？”，“这段代码需要重构吗？”

*   最常写的crud 和 通用的代码完全可以交给 AI，不像自己写时还有可能 复制粘贴错误.

*   让它告诉我们如何写出更加健壮，可读性强的代码，因为我觉得它在学习了 GitHub 上那么多优秀的开源库后，它提供的基本上都是最佳实践，我们只需要写出更好的 prompt 即可

Copilot的确是一个很有意思的工具，但是目前还处于测试阶段，建议大家在生产环境中谨慎使用，因为Copilot的建议不一定是正确的，有可能会导致一些安全问题。但是Copilot的确可以帮助我们提高编程效率，减少一些机械性、繁琐的任务，让我们更加专注于业务逻辑的实现。对于使用Copilot生成的代码一定要进行严格的测试，保证代码的正确性和安全性。

接下来, 我会继续分享更多精彩的的使用方法, 欢迎与我交流，希望我们可以一起学习和探讨.