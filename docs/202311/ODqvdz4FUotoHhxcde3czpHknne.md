# 如何使用ChatGPT写脚本无限注册heygen，实现数字人自由？

> 来源：[https://ia0969wpr2.feishu.cn/docx/ODqvdz4FUotoHhxcde3czpHknne](https://ia0969wpr2.feishu.cn/docx/ODqvdz4FUotoHhxcde3czpHknne)

我们都知道最近一段时间heygen非常火爆，特别是在抖音上，不少小和尚和心灵鸡汤内容都是通过heygen制作的。然而，heygen的免费账号仅提供一个credit，一旦用完就需要手动注册新账号。那我能不能通过ChatGPT写脚本实现批量注册呢？

实操下来，与ChatGPT对话一个多小时后我完成了v1.0版本，当然这个脚本还有需要要完善的地方，但是对于个人自用来说已经完全没有问题了，试了一下半小时不到就生成了二十多个账号。

通过与ChatGPT对话的过程实现整个需求来看，即使是编程新手，也可以通过自然语言交互实现自动化需求。那举一反三更进一步，通过结合GPT-4和GitHub Copilot，能不能使用ChatGPT写脚本抓取小红书或者推特上的数据？能不能抓取公众号所有的十万加的文章？能不能批量自动化使用heygen制作视频？答案是可以的，也并不难做到，我们需要付出的就是多一点的耐心。

如果没有GPT4或者github copilot怎么办呢？接下来给大家推荐免费的平替，他们的效果甚至比GPT4+Copilot的组合更好，这些工具主要专注于编程领域，针对代码生成进行了特定的微调，因此在代码生成方面有更大的优势。那就是Code-Llama-34B 和 replit AI，Code-Llama我们可以在poe免费使用，缺点是不支持中文回复。replit在上个月也宣布了免费计划，和订阅版比起来，replit 免费版没有办法创建私有仓库，不过对于轻度使用完全没问题。

接下来我分享的就是如何从零开始利用ChatGPT实现heygen的批量注册，实现数字人自由。整个过程中，我们完全依赖GPT生成脚本，所有代码都是由GPT生成。

## 需求分析

首先我们需要告诉ChatGPT我们的需求，要求他评估整个自动化过程中需要用到的工具和资源，以及需要我们提供哪些信息。

![](img/6f775a23c9e58e7c196867445c57b336.png)

通过GPT的回答，我们可以得到以下信息：

为了完成一个基本的账号自动化注册，我们需要：

1\. 可以使用selenium模拟浏览器操作

2\. 拥有一个可以无限接收验证码的邮箱服务

至于验证码、IP地址和代理的问题，目前可以暂时不考虑。如果未来heygen对此有所限制或者在批量注册账号时遇到问题，我们可以手动更换代理或修改代码。但在目前阶段，这些可以先忽略。

上面第一点中，我们可以让GPT帮助我们生成操作浏览器的代码。那么第二点，如何获取无限的邮箱呢？以Gmail为例，example@gmail.com 中的 gmail.com 是域名，前缀是邮箱地址。也就是只要我们拥有了域名，理论上就可以搭建自己的邮箱服务，从而获得无限的地址。所以接下来的目标就是有没有最简单的搭建自己邮箱服务器的方法呢？

![](img/6fc146098f237aa1bd31b119071b368a.png)

![](img/cebacbf584d3c78cf8eef75436d6bc1c.png)

![](img/38087dd6c7d5b966ca0e1a9a12c25baa.png)

通过与GPT的对话我们再次得到了几个关键信息：

*   只要拥有了域名，我们就可以设置一个捕获所有邮件（catch-all）的邮箱地址，不管发送到你域名下的任何前缀（如[anything]@yourdomain.com）的邮件，都会被路由到一个指定的邮箱。这样我们只需要从这个指定邮箱中根据发件人和收件人查询到heygen的注册邮件并且提取验证码就可以了。

*   设置catch-all邮箱的最简单方式可以使用邮件转发服务，比如ImprovMX 和 Forward Email（当然也可以使用第三方邮件服务，但是可能会有一些限制，优点就是上手门槛更低）

也就是说我们只需要一个域名，用于生成无限邮箱，其他的GPT都可以帮助我们完成。

下一步就是注册自己的域名。

## 域名注册与邮箱服务搭建

首先我们可以去cloudflare或者namesilo 或者其他任何自己熟悉的域名注册商注册自己的域名，最便宜的域名只需要几块钱，我们按需购买即可。如果有自己的域名那就更好了。

这里我以一个自己的域名为例：bardextension.io。

根据刚才GPT的推荐，这里我选择使用forwardemail进行catch-all邮件的转发。我们首先访问 https://forwardemail.net/ ，如果没有注册的话我们可以直接使用gmail第三方登录。

![](img/0e436d4e898f80448605966b7dfb5b70.png)

登录成功之后我们点击add domain添加我们的域名，比如这里填入我自己的域名bardextension.io

![](img/165eb8e1680e4446f9934ec7ca9a8e60.png)

点击继续后出现下面的引导配置页面：

![](img/ca6d25b308784682f5c757c8221d172a.png)

![](img/7ffd30a05edb689ac85c07498f4213e3.png)

接下来我们就可以登录到我们的域名后台根据引导页修改DNS了，红框中的MX地址是必须要新增的，我们需要把所有的邮箱都路由到同一个邮箱中，这里推荐使用自己的gmail邮箱。

接下来我们就可以去新增DNS记录了，因为我的bardextension.io 域名是在namesilo注册的，我们进入到namesilo后台，在下面的红框区域填写对应的解析信息。

![](img/dcefad6a1e3ebd1907047799de14bd71.png)

![](img/270be988f9448f73cc5ce53e172e1ab8.png)

OK，填写完成之后我们返回到forwardemail的引导页，点击verify

![](img/d86c920bcf3b07f75e44438b62d1d6c6.png)

点击后如果上面出现了congratulations，说明已经验证成功了，这时候我们的无限邮箱就算完成了，接下来不管你发送到邮件到 [anything]@bardextension.io 的任何地址，都会转发到你DNS中刚刚配置的forwardemail的邮箱中，这里你可以测试一下了，比如发送邮件到test@@bardextension.io，你可以在自己的gmail中看到了。

![](img/a6525049ff3080ca0880cd277e6aff46.png)

搭建完成邮箱之后我们就要进入到下一步了，我们需要如何从邮箱中获取验证码并且自动化呢？我们继续问ChatGPT

## 自动化获取验证码

![](img/0e8a61a160414a696c463bd6501144f8.png)

![](img/0d7f3644968a6ff432165cb04a27db84.png)

通过与GPT的对话我们大概了解到了自动获取验证码的方式，那就是使用Gmail API 或者 IMAP的方式在邮箱中搜索特定的邮件然后提取验证码，这两种方式都可以，这里我选择使用IMAP的方式。

我们让GPT联网查询Gmail如何配置IMAP，根据教程我们进行以下配置：

首先找到 "所有设置" 按钮，点击后选择 "开启IMAP"

![](img/6d8357917871eed68b0a1675f012b4a2.png)

![](img/85743a45ab694d1358d89ca55e293fe8.png)

开启后直接选择保存我们的更改，这里IMAP设置就已经完成了！设置好IMAP之后，我们让GPT实现从Gmail中获取heygen的验证码：

![](img/acbd55721cf7a0cac9ac06e1e7a3ff49.png)

我们把GPT实现的代码拷贝出来并且在本地执行：

```
import imaplib
import email
from email.header import decode_header
import re

def fetch_verification_code(gmail_user, gmail_password, sender, recipient):
    """
    Fetches a six-digit verification code from Gmail using IMAP.

    Parameters:
    gmail_user (str): Gmail username.
    gmail_password (str): Gmail password.
    sender (str): Email address of the sender.
    recipient (str): Email address of the recipient.

    Returns:
    str: The six-digit verification code, if found. Otherwise, returns None.
    """

    # Connect to Gmail IMAP server
    imap_url = 'imap.gmail.com'
    mail = imaplib.IMAP4_SSL(imap_url)
    mail.login(gmail_user, gmail_password)

    # Select the inbox
    mail.select('inbox')

    # Search for emails from sender to recipient
    status, messages = mail.search(None, f'(FROM "{sender}" TO "{recipient}")')

    # Check if any messages are found
    if status != 'OK':
        print("No messages found.")
        return None

    # Fetch messages
    for num in messages[0].split():
        typ, data = mail.fetch(num, '(RFC822)')
        if typ != 'OK':
            print(f"ERROR: Unable to fetch email {num}.")
            continue

        # Parse the email content
        msg = email.message_from_bytes(data[0][1])
        if msg.is_multipart():
            for part in msg.walk():
                content_type = part.get_content_type()
                content_disposition = str(part.get("Content-Disposition"))

                # Extract body
                if "attachment" not in content_disposition and content_type == "text/plain":
                    body = part.get_payload(decode=True).decode()
                    # Search for a six-digit code in the email body
                    code = re.search(r'\b\d{6}\b', body)
                    if code:
                        return code.group()

    return None

# Example usage
# Note: Replace 'your_username', 'your_password', 'sender@example.com', and 'recipient@example.com' 
# with actual values before running this function.
# code = fetch_verification_code('your_username', 'your_password', 'sender@example.com', 'recipient@example.com')
# print(code)

```

这时我们发现需要填写用户名和密码，用户名是我们的Gmail邮箱，那这个密码是什么，需要在哪里获取呢？不知道？没关系，继续问ChatGPT：

![](img/e9f944b944cd4fb2fa15658d0e170088.png)

好的，GPT已经告诉我们如何获取密码了，我们进行两步验证之后直接选择设置专用密码：

![](img/980d1fc6b423e96ef6bf9c9e144af26b.png)

![](img/1234d2cadc6f5649f858647ab4c5c057.png)

填写App name，这里可以随便写一个作为我们的应用名称，这个应用名称只是一个标记没有其他的作用，点击创建后我们就可以获取到专用密码了，这时候回填到脚本中执行测试测试一下，完全没问题。但是执行起来有些慢，我们需要加快些速度，继续要求GPT修改：

![](img/50c407fb813139d00296d47b515c397b.png)

自动化获取邮箱验证码完整代码如下：

```
import imaplib
import email
from email.header import decode_header
import re

def fetch_latest_verification_code(gmail_user, gmail_password, sender, recipient):
    """
    Fetches a six-digit verification code from the latest 10 unread emails in Gmail using IMAP.

    Parameters:
    gmail_user (str): Gmail username.
    gmail_password (str): Gmail password.
    sender (str): Email address of the sender.
    recipient (str): Email address of the recipient.

    Returns:
    str: The six-digit verification code, if found. Otherwise, returns None.
    """

    # Connect to Gmail IMAP server
    imap_url = 'imap.gmail.com'
    mail = imaplib.IMAP4_SSL(imap_url)
    mail.login(gmail_user, gmail_password)

    # Select the inbox
    mail.select('inbox')

    # Search for unread emails from sender to recipient in the latest 10 emails
    status, messages = mail.search(None, f'(FROM "{sender}" TO "{recipient}" UNSEEN)')
    if status != 'OK':
        print("No unread messages found.")
        return None

    # Fetch latest 10 messages
    message_numbers = messages[0].split()[-10:]
    for num in message_numbers:
        typ, data = mail.fetch(num, '(RFC822)')
        if typ != 'OK':
            print(f"ERROR: Unable to fetch email {num}.")
            continue

        # Parse the email content
        msg = email.message_from_bytes(data[0][1])
        if msg.is_multipart():
            for part in msg.walk():
                content_type = part.get_content_type()
                content_disposition = str(part.get("Content-Disposition"))

                # Extract body
                if "attachment" not in content_disposition and content_type == "text/plain":
                    body = part.get_payload(decode=True).decode()
                    # Search for a six-digit code in the email body
                    code = re.search(r'\b\d{6}\b', body)
                    if code:
                        return code.group()

    return None

# Example usage
# Note: Replace 'your_username', 'your_password', 'sender@example.com', 'recipient@example.com' 
# with actual values before running this function.
# code = fetch_latest_verification_code('your_username', 'your_password', 'sender@example.com', 'recipient@example.com')
# print(code)

```

以上为获取无限邮箱且实时获取验证码的逻辑，接下来就是heygen自动化注册部分了

## 实现自动化注册

通过刚刚GPT写的代码，我们知道获取验证码的方法为fetch_verification_code，我们再次把注册的过程和heygen网站的要求告诉GPT，让他为我们生成代码：

![](img/fe39ac7249e0c5772b3cf3beb1a76269.png)

拷贝代码本地运行，发现浏览器已经打开了并且走到了注册环节，但是没有输入邮箱，这又是怎么回事？把问题抛给GPT：

![](img/b9be016bb5e4ee732b505c675d271a8e.png)

定位xpath之后发给ChatGPT，最终生成的代码如下，本地运行，发现除了验证码以外已经完美实现！

## 整合验证码

上一步生成的代码已经实现了自动化过程，但是验证码还没有整合进来，我们直接把第一步生成的代码拷贝到第二个脚本中即可，完整代码如下：

```
import random
import string
import time

from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import imaplib
import email
from email.header import decode_header
import re

gmail_user = "xxxx@gmail.com"
gmail_password = "xxxxxx"

def fetch_verification_code(sender, recipient, max_messages=10):
    """
    Fetches a six-digit verification code from Gmail using IMAP.

    Parameters:
    gmail_user (str): Gmail username.
    gmail_password (str): Gmail password.
    sender (str): Email address of the sender.
    recipient (str): Email address of the recipient.

    Returns:
    str: The six-digit verification code, if found. Otherwise, returns None.
    """

    # Connect to Gmail IMAP server
    imap_url = 'imap.gmail.com'
    mail = imaplib.IMAP4_SSL(imap_url)
    mail.login(gmail_user, gmail_password)

    # Select the inbox
    mail.select('inbox')
    print("begin search")
    # Search for emails from sender to recipient
    # status, messages = mail.search(None, '(UNSEEN)', f'(FROM "{sender}")', f'(TO "{recipient}")')
    status, messages = mail.search(None, f'(FROM "{sender}" TO "{recipient}")')
    print(messages)

    # Check if any messages are found
    if status != 'OK':
        print("No messages found.")
        return None

    # Fetch messages
    messages = messages[0].split()[-max_messages:]
    for num in messages:
        print(f"Fetching email {num}...")
        typ, data = mail.fetch(num, '(RFC822)')
        if typ != 'OK':
            print(f"ERROR: Unable to fetch email {num}.")
            continue

        # Parse the email content
        msg = email.message_from_bytes(data[0][1])
        if msg.is_multipart():
            for part in msg.walk():
                content_type = part.get_content_type()
                content_disposition = str(part.get("Content-Disposition"))

                # Extract body
                if "attachment" not in content_disposition and content_type == "text/plain":
                    body = part.get_payload(decode=True).decode()
                    print(f"body is :{body}")
                    # Search for a six-digit code in the email body
                    code = re.search(r'\b\d{6}\b', body)
                    if code:
                        return code.group()

    return None

# 随机生成邮箱地址
def generate_email(domain, length=10):
    characters = string.ascii_letters + string.digits
    email_local_part = ''.join(random.choice(characters) for i in range(length))
    return email_local_part + "@" + domain

# 随机生成密码
def generate_password(length=12):
    characters = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(characters) for i in range(length))
    return password

# 主函数
def main():
    email = generate_email("bardextension.io", random.randint(5, 10))
    password = generate_password(random.randint(12, 18))

    # 初始化 WebDriver
    driver = webdriver.Chrome()
    driver.get("https://app.heygen.com/login")

    try:
        # 点击 Sign Up with Email
        WebDriverWait(driver, 10).until(
            EC.element_to_be_clickable((By.LINK_TEXT, "Sign Up with Email"))
        ).click()
        print("click sign up with email")

        # 输入邮箱地址并发送验证码
        WebDriverWait(driver, 10).until(
            EC.visibility_of_element_located((By.ID, "email"))
        ).send_keys(email)
        driver.find_element(By.XPATH, "//button[.//span[contains(text(), 'Send Code')]]").click()
        print("send code")

        time.sleep(10)
        # 假设使用 fetch_verification_code 函数获取验证码
        code = fetch_verification_code("no_reply@mail.heygen.com", email)
        if(code is None):
            print("未获取到验证码，正在重试中")
            time.sleep(20)
            code = fetch_verification_code("no_reply@mail.heygen.com", email)

        # 填写验证码并点击 Next Step
        WebDriverWait(driver, 10).until(
            EC.visibility_of_element_located((By.ID, "code"))
        ).send_keys(code)
        print("code is :", code)
        driver.find_element(By.XPATH, "//button[.//span[contains(text(), 'Next Step')]]").click()
        print("next step")

        # 输入密码并完成注册
        WebDriverWait(driver, 10).until(
            EC.visibility_of_element_located((By.ID, "password"))
        ).send_keys(password)

        WebDriverWait(driver, 10).until(
            EC.visibility_of_element_located((By.ID, "pwdConfirm"))
        ).send_keys(password)

        driver.find_element(By.XPATH, "//button[.//span[contains(text(), 'Done')]]").click()
        print(f"email: {email}, password: {password}")

        # 关闭浏览器
        driver.quit()
    except Exception as e:
        print("发生错误：", e)
        driver.quit()

if __name__ == "__main__":
    main()
```

启动后发现已经注册成功：

![](img/36a49b0d97464f61147ed98e1e91ae26.png)

## 保存生成的账号信息

接下来我们要保存我们的账号到一个Excel中，并且要做到批量注册，那我们要怎么做呢？把刚刚的代码扔回给ChatGPT，让他们帮我继续下一步：

![](img/befcaef8ab832f5d41791d7ff5ce4e8c.png)

![](img/3e40d3b0845c457963b6c374afc9207f.png)

完美，到此为止，这个脚本已经实现了我们的功能，但是这时候仍然有一个问题，就是现在是每5个账号就生成一个Excel，我需要让他把所有的账号写到一个Excel中，只是每5个保存一次而已，继续让他改。

![](img/398cdc7df336c4fa9df84764e2ec3bbf.png)

执行后发现符合我们需求，到这里实际上整个脚本就已经完成了，但是我们可以再次添加一些验证信息，去掉自动化标识，使整个操作看起来更像人类执行：

![](img/532b33b436db6ee747c959a421f53eb0.png)

完整代码如下：

```
import random
import string
import time

from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import imaplib
import email
from fake_useragent import UserAgent
import pandas as pd
import re

gmail_user = "xxxxxx@gmail.com"
gmail_password = "xxxxxxxx"

def create_driver():
    """
    创建并配置WebDriver。
    """
    options = webdriver.ChromeOptions()
    # Add arguments for ChromeOptions to make the browser more "real"
    options.add_argument("--disable-blink-features=AutomationControlled")
    options.add_argument("--start-maximized")
    options.add_argument("--disable-infobars")
    options.add_argument("--disable-extensions")
    options.add_argument("--no-sandbox")
    options.add_argument("--disable-dev-shm-usage")
    options.add_argument("--headless")
    ua = UserAgent()
    user_agent = ua.random
    options.add_argument(f"user-agent={user_agent}")
    options.add_experimental_option("excludeSwitches", ["enable-automation"])

    driver = webdriver.Chrome(options=options)
    driver.execute_script("Object.defineProperty(navigator, 'webdriver', {get: () => undefined})")

    return driver
def fetch_verification_code(sender, recipient, max_messages=10):
    """
    Fetches a six-digit verification code from Gmail using IMAP.

    Parameters:
    gmail_user (str): Gmail username.
    gmail_password (str): Gmail password.
    sender (str): Email address of the sender.
    recipient (str): Email address of the recipient.

    Returns:
    str: The six-digit verification code, if found. Otherwise, returns None.
    """

    # Connect to Gmail IMAP server
    imap_url = 'imap.gmail.com'
    mail = imaplib.IMAP4_SSL(imap_url)
    mail.login(gmail_user, gmail_password)

    # Select the inbox
    mail.select('inbox')
    print("begin search")
    # Search for emails from sender to recipient
    status, messages = mail.search(None, '(UNSEEN)', f'(FROM "{sender}")', f'(TO "{recipient}")')
    # status, messages = mail.search(None, f'(FROM "{sender}" TO "{recipient}")')

    # Check if any messages are found
    if status != 'OK':
        print("No messages found.")
        return None

    # Fetch messages
    messages = messages[0].split()[-max_messages:]
    for num in messages:
        print(f"Fetching email {num}...")
        typ, data = mail.fetch(num, '(RFC822)')
        if typ != 'OK':
            print(f"ERROR: Unable to fetch email {num}.")
            continue

        # Parse the email content
        msg = email.message_from_bytes(data[0][1])
        if msg.is_multipart():
            for part in msg.walk():
                content_type = part.get_content_type()
                content_disposition = str(part.get("Content-Disposition"))

                # Extract body
                if "attachment" not in content_disposition and content_type == "text/plain":
                    body = part.get_payload(decode=True).decode()
                    # Search for a six-digit code in the email body
                    code = re.search(r'\b\d{6}\b', body)
                    if code:
                        return code.group()

    return None

# 随机生成邮箱地址
def generate_email(domain, length=10):
    characters = string.ascii_letters + string.digits
    email_local_part = ''.join(random.choice(characters) for i in range(length))
    return email_local_part + "@" + domain

# 随机生成密码
def generate_password(length=12):
    characters = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(characters) for i in range(length))
    return password

# 主函数
def register_account():
    """
    注册单个账号并返回邮箱和密码。
    """
    email = generate_email("bardextension.io", random.randint(5, 10))
    password = generate_password(random.randint(12, 18))

    # 初始化 WebDriver
    driver = create_driver()
    driver.get("https://app.heygen.com/login")

    try:
        time.sleep(random.randint(1, 3))
        # 点击 Sign Up with Email
        WebDriverWait(driver, 10).until(
            EC.element_to_be_clickable((By.LINK_TEXT, "Sign Up with Email"))
        ).click()
        print("click sign up with email")

        time.sleep(random.randint(1, 3))
        # 输入邮箱地址并发送验证码
        WebDriverWait(driver, 10).until(
            EC.visibility_of_element_located((By.ID, "email"))
        ).send_keys(email)
        driver.find_element(By.XPATH, "//button[.//span[contains(text(), 'Send Code')]]").click()
        print("send code")

        time.sleep(random.randint(5, 10))
        # 假设使用 fetch_verification_code 函数获取验证码
        code = fetch_verification_code("no_reply@mail.heygen.com", email)
        if(code is None):
            print("未获取到验证码，正在重试中")
            time.sleep(20)
            code = fetch_verification_code("no_reply@mail.heygen.com", email)

        # 填写验证码并点击 Next Step
        WebDriverWait(driver, 10).until(
            EC.visibility_of_element_located((By.ID, "code"))
        ).send_keys(code)
        time.sleep(random.randint(1, 3))
        print("code is :", code)
        driver.find_element(By.XPATH, "//button[.//span[contains(text(), 'Next Step')]]").click()
        print("next step")

        # 输入密码并完成注册
        WebDriverWait(driver, 10).until(
            EC.visibility_of_element_located((By.ID, "password"))
        ).send_keys(password)

        WebDriverWait(driver, 10).until(
            EC.visibility_of_element_located((By.ID, "pwdConfirm"))
        ).send_keys(password)
        time.sleep(random.randint(1, 3))
        driver.find_element(By.XPATH, "//button[.//span[contains(text(), 'Done')]]").click()
        print(f"email: {email}, password: {password}")

        # 关闭浏览器
        driver.quit()
        return email, password
    except Exception as e:
        print("发生错误：", e)
        driver.quit()
        return None, None

def main():
    all_accounts = pd.DataFrame()  # 初始化一个空的DataFrame
    for _ in range(100):  # 循环100次
        email, password = register_account()
        if email and password:
            new_account = pd.DataFrame({'Email': [email], 'Password': [password]})
            all_accounts = pd.concat([all_accounts, new_account], ignore_index=True)

            # 每5个账号保存一次
            if len(all_accounts) % 2 == 0:
                all_accounts.to_excel('all_accounts.xlsx', index=False)

if __name__ == "__main__":
    main()
```

开始启动脚本测试，午饭回来已经注册了二十个账号（附在下面）。但这时又发现了一个比较烦人的事情，每次启动脚本都会打开浏览器操作，让我干不了别的工作了，怎么办？问ChatGPT呗，加一个headless，完美解决。收工！

## 总结

以上整个过程不到两个小时，我们得到了以下东西：

1.  一个完整的自动化注册heygen脚本

1.  不限量的个人邮箱，不仅可以用来注册heygen，也可以后续注册其他的海外服务

那我们付出了什么呢？是的，一个多小时的时间和一个域名的成本，最便宜的域名可能只需要十几块钱。当然这个脚本还很简陋，比如没有可视化操作，还需要使用到命令行启动。比如还不能创建12积分的账号，但这些问题通过ChatGPT依然可以很快地解决。如果大家感兴趣，欢迎留言交流，我会整理一下分享后续如何使用GPT实现可视化和12积分账号的注册。

使用GPT帮我们自动化过程中的一些小技巧：

当两轮对话解决不了问题的时候，及时切换到新的对话窗口，这样可以快速解决我们的问题。

另外就是生成的回答不满意的时候，我们点击下方的重新生成答案，一定要多重试几次，可能会有惊喜。

最后本文只是为了展示ChatGPT的应用案例，不鼓励任何违反网站协议的自动化行为，仅仅用于学习和教育目的。