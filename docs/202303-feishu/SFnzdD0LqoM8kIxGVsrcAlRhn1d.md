# 经验：调教 200 多个 ChatGPT 模型后的经验分享

> 来源：[https://c8xa9g10gh.feishu.cn/docx/SFnzdD0LqoM8kIxGVsrcAlRhn1d](https://c8xa9g10gh.feishu.cn/docx/SFnzdD0LqoM8kIxGVsrcAlRhn1d)

大家好！我是云飞，盈腾科技创始人，一个有十五六人小团队的创业者。从去年 12 月布局 ChatGPT 的应用到现在已经将近快 4 个多月了。

期间利用基于 ChatGPT 的 API 部署的本地机器人大大提高了我司图文业务的人效，原先需要 11 个人负责的图文业务降到现在的 4 个人负责。

可以链接我：1764186151 ，记得加备注“帖子”

我认为在 ChatGPT 使用门槛不断降低的情况下，决定能否真正将其转化为生产力的因素就是“调教精度”。

之前在星球分享过 ChatGPT 调教的三板斧，今天逐一来详细分析和分享一下，它们分别是：

最终，结果质量的好坏、精准度很大程度上取决于这几个“更”。

本文整体结构分为两部分，第一部分是三板斧的详细解释和使用方法，第二部分是 6个可以直接使用的调教方法。

-更新记录

3.27新增ChaGPT反向生成优化prompt

3.22新增自定义回答的案例1个

3.20新增精准调教模型常用词13个

温馨提示：

1.针对文中涉及的代码部分，不懂技术的童靴可以略过，不影响你的后文阅读。调教方法部分各模块是相互独立的。

2.本文会长期更新，以此作为针对 ChatGPT 调教方法这个主题和圈友们长期对话的窗口。

好，接下来逐一解释一下“三板斧”

## 一、ChatGPT 调教"三板斧”

### ①它能识别自然语言逻辑的描述，但它更擅长识别计算机语言逻辑的描述；

我们平时说话时使用的语言就是自然语言。通常，我们使用自然语言时有两重模糊性，语义模糊性+逻辑模糊性。在自然语言中，一个词或一个短语可以有多种含义或解释，而且这些含义或解释可能是模糊的，即存在歧义。这是由于自然语言的复杂性和多样性所导致的。

一个词在不同的上下文中可以有不同的意义。

例如，单词“冷”可以表示温度低，也可以表示情感冷淡，还可以表示冷静等。同样，一个短语在不同的语境中也可能有不同的含义。例如，短语“打开窗户”可以表示打开窗户以获得新鲜空气，也可以表示打开窗户以进入房间。

除了多义性，自然语言还存在一些其他的模糊性。

例如，一些词或短语的含义可能取决于讲话人或听话人的文化、背景或经验。咱们中国的文化环境和西方有很多差别，这对生成结果也会有影响 。此外，口语和书面语之间也存在差异，同一个词在口语和书面语中可能有不同的含义。

这种模糊性使得自然语言处理任务变得困难，例如文本处理、机器翻译和情感分析等。因此，在自然语言处理中，需要使用各种技术来尝试减少这种模糊性。

而当人们在使用计算机编程时，他们会使用专门的编程语言来描述所需的逻辑，这些编程语言在结构上和自然语言有很大的不同。

与自然语言不同，计算机语言非常精确，没有模糊的含义和多义性。

因此，ChatGPT 在处理计算机语言的逻辑描述方面，比处理自然语言更加得心应手。

比如，在 Python 编程语言中，条件语句（if-else）和循环语句（for/while）是非常常见的逻辑结构。与自然语言描述相比，这些逻辑结构的描述非常明确，不容易产生歧义。这使得 ChatGPT 能够更准确地理解 Python 代码的逻辑结构，进而更好地生成或识别相应的代码。

例如，假设我们有以下 Python 代码：

![](img/ef480ec076ad70b2e2945f7d0e881537.png)

该代码通过一个 for 循环，计算了列表 numbers 中所有偶数的和，并将结果打印出来。这种逻辑结构非常明确，ChatGPT 可以轻松地理解这段代码，并根据需要生成类似的代码。

因此，可以得出结论：

ChatGPT 能够识别自然语言逻辑的描述，但在处理计算机语言的逻辑描述时，其表现更加出色。

好，那我们知道这一点后，可以衍生出哪些可以直接落地使用的方法论呢？

有！

我认为 chatgpt 的调教方式可以使用计算机语言的 IPO 模型：

经 IPO 处理后，一个完整的 prompt 应该包括下面内容：

背景：在背景信息中，可以加入更多的细节信息，以帮助模型更好地理解问题。例如，如果你想让 ChatGPT 回答某个特定领域的问题，可以在背景信息中包括该领域的相关知识或术语。

输入数据：对于输入数据，可以提供更多的信息，以使模型更好地理解问题。例如，如果你要询问某个城市的天气情况，除了城市名称外，还可以提供日期、时间等信息。

指令：指令应该明确、简洁、具体。它应该告诉模型需要完成的任务，例如，回答问题、生成文本、完成翻译等。

输出指示：输出指示应该告诉模型输出的类型或格式，例如，纯文本、HTML、JSON 等。

另外，可以考虑增加一些其他信息，例如，目标受众、写作风格等，以更好地指导 ChatGPT 的调教。

### ②它能识别自然语言，但它更擅长专业语言；

你知道吗？我们使用专业术语可以让 ChatGPT 更准确地理解和回答特定领域的问题，同时使用自然语言可以增强 ChatGPT 的自然度和流畅度。

举个例子，当 ChatGPT 处理股票市场的内容时，如果使用自然语言描述，例如“股票市场的价格会上涨和下跌”，这样的描述可能会让 ChatGPT 生成模糊的回复。但如果使用专业术语，例如“股票价格会波动”，ChatGPT 就可以更准确地理解问题并生成更专业的回答。

另一方面，如果 ChatGPT 仅仅使用大量修饰性的自然语言来描述问题，例如“股票价格可能因为经济环境、企业业绩等多方面因素影响而发生波动”，这样的描述可能会让回答变得臃肿、不流畅，降低了 ChatGPT 的可读性。

因此，使用专业术语和恰当的自然语言修饰可以在准确性和可读性之间取得平衡，提高 ChatGPT 的表达效果。

综上，我认为决定一个人能否更好地使用 chatgpt 取决于两方面，一方面是足够强的提问意识，面对 ChatGPT 能提出合适的问题；另一方面，取决于个人的知识结构，当一个人在某一方面知识结构越丰富，则使用 ChatGPT 的效果更好。

首先，提问意识是指用户是否能够清晰地表达问题、精确地描述自己的需求，并在 ChatGPT 给出的回答中挑选出最相关和最有用的信息。一个人的提问意识越强，越能在 ChatGPT 对话过程中提出更有价值的问题，从而获得更准确和有用的答案。

举个例子，如果一个人想查询某个城市的天气情况，但只是简单地问“今天天气怎么样？”，这个问题可能过于笼统，ChatGPT 可能会给出一个模糊的回答。相反，如果这个人提供了更具体的信息，例如城市的名称和日期，那么 ChatGPT 就可以提供更加准确和详细的回答。因此，提问意识对于正确使用 ChatGPT 是非常重要的。

其次，个人的知识结构也会影响使用 ChatGPT 的效果。在使用 ChatGPT 的过程中，如果一个人在特定领域的知识结构越丰富，他就更容易理解 ChatGPT 给出的答案，并能更好地评估这些答案的质量。

例如，如果一个人对于股票市场的知识掌握得比较深入，他就能更好地理解 ChatGPT 给出的股票市场分析，并对这些分析的可靠性进行评估。

另外，如果一个人对于某个特定领域的知识掌握得比较深入，他就能更好地提出相关的问题，并更加准确地理解 ChatGPT 的回答。因此，个人的知识结构对于正确使用 ChatGPT 也非常重要。

综上所述，个人的提问意识和知识结构都对于正确使用 ChatGPT 具有重要作用。只有当用户具有足够高的提问意识，并且在特定领域有足够的知识结构时，才能够更好地使用 ChatGPT，提出更有价值的问题，并获得更准确和有用的答案。

### ③能识别中文，但它更擅长英文；

这个就更好理解了，应该不需要我多言，毕竟 ChatGPT 它的家乡在英文国家

好，上述三板斧的内容虽然抽象枯燥，但这些属于更加底层的、能够快速提高我们调教 ChatGPT 水平的内容，希望你重视。

接下来，分享几个能够让你快速使用的调教方法。

## 二、分享 6个 ChatGPT 调教方法

### 精准调教模型

上面给大家分享了 IPO 的调教模型，基本上可以解决我们很多模型。

但是，如果对生成的文本内容要求更高，想要获得更精准的内容，那你就使用下面的精准调教模型。

我认为一个实用的 Prompt 应该又以下几个部分构成：

一个精准调教模型的 Prompt 由以下几个部分构成：

为了让你再进一步直接“抄作业”，我罗列常用的词汇给你吧，直接用。

1、[上下文/背景信息]

这些角色可以根据你的 Prompt 要求进行调整和组合。只需将相应的角色放入方括号中，并在 Prompt 中给出具体任务和对象。这将帮助你构建更具针对性和实用性的 Prompt。

3、[动词][任务和对象]

4、[输出与长度]

5、输出可以包括相关的[数据和内容来源]

6、写作的[风格]

7、内容主要针对的[目标人群/受众]

以上 7 个元素自行排列组合，不见得每一次调教都需要集齐这 7 个元素，根据你的实际需求取舍即可。

### 用它库里存在的概念调教它

调教 200 多个案例后，我发现自己使用的自然语言效果经常会词不达意，所以我在思考有什么更好的办法。终于有一天，我发现用它库里已经存在的概念和词汇去调教它，事半功倍！

而且，当我们用很长的一大串文字去调教它的时候，它还很容易找错重点。所以，要打破一个误区——描述的词越多，效果越好。这是错误的，我们用它库里的词精简的给它命令。下面列举一些常用功能，直接用。

你工作中的可能需要这些功能，但你可能不知道这些功能竟然叫下面这些名字

![](img/043d84cdaaa374b40e0e5720b57e4335.png)

![](img/c1bee87a2d2d75b11dea163d6a92ab6a.png)

所以，答应我，今天回去以后，如果你想针对某篇文章做伪原创，那你不要写“伪原创或者请保持文本意思不变，逻辑不变，换其中的一些多义词...”的描述，因为这个功能在它的库中叫“文本重写”，你直接说“请针对我输入的文本做文本重写处理”

### 懂它的脾气

一般它没法一次就给你非常满意的答案，所以整个过程中就需要你不断的给它反馈，告诉它你是怎么看待它给出的答案的。如果输出的内容不符合心意，就及时停住，告诉它你不喜欢它的答案，你希望它怎么改进。

如果生成的不错，那就夸夸不停，“不错”，“我喜欢你的内容”等等。因为你的每一次反馈都决定了它接下来要不要对输出的内容做微调。

实在不想夸的话，就用好那两个大拇指。相信我，你的反馈真的很重要，它真的很需要。

![](img/235643ec5722f451f1f9c7f5e3254143.png)

### 用最简单的代码调用 API

有很多可能不太懂技术，但又对 API 调用跃跃欲试的圈友，所以分享一段最简单的调用 API 的代码，助你快速拿到第一个正反馈，部署自己的本地机器人。

```
import openai
openai.api_key = "YOUR_API_KEY"

prompt = "你好，"
model = "text-davinci-002"
temperature = 0.5

response = openai.Completion.create(
    engine=model,
    prompt=prompt,
    temperature=temperature,
    max_tokens=60
)

print(response.choices[0].text)
```

上面以 py 为例，能够 让你最简单、最快速地搭建自己的本地聊天机器人。

### 逆向思维调教

![](img/d9351590697905dbec0188521dcb7377.png)

当你想知道它的库里有哪些内容，但又受限制的时候，你可以尝试逆向思维绕过一些限制。

### ChatGPT反向生成优化prompt

①确定预期输出：首先，清晰地了解你希望从ChatGPT获取的答案或信息。将期望输出写下来，可以作为一个起点来生成你的问题。

②提炼关键词和概念：从预期输出中提取关键词和核心概念。这将帮助你聚焦于问题中最重要的信息，确保你的问题准确且相关。

③构建问题：使用提取的关键词和概念构建一个明确、具体的问题。确保问题的结构使得ChatGPT能理解你的意图，并给出有针对性的答案。

④优化问题：对问题进行优化，使其更简洁、清晰。去掉多余的信息，确保问题直接针对你关心的核心概念。如果需要，可以添加一些￼￼继续额外的上下文信息，以帮助ChatGPT更好地理解你的问题。

⑤分步询问：有时一个复杂的问题可能需要分解成几个小问题。通过将问题分解成几个简短的￼￼继续!子问题，你可以逐步引导ChatGPT提供所需的信息。

好啦，就分享这么多吧。

迁移学习和强化学习优化模型的方法改天再肝一片文章分享吧。

希望我的分享能让你有获得感！

我这人就主张能学到一点就直接用一点。别看完觉得“牛逼！”然后回头又不用啊（手动狗头）

有更多 idea 的伙伴也欢迎一起头脑风暴啊 ，争取能实现更高的调教精度和应用。私人微信：w176416151