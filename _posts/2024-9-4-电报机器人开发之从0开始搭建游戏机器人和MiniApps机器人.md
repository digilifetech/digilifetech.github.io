---
layout:     post   				    # 使用的布局（不需要改）
title:      电报机器人开发之从0开始搭建游戏机器人和MiniApps机器人				# 标题 
subtitle:   以彩票游戏为基础演示从0开始搭建一套电报游戏机器人和telegram miniapps #副标题
date:       2024-9-4				# 时间
author:     队长游戏 						# 作者
header-img: img/lotto_tongji.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:
    - MiniApps								#标签
    - 电报游戏机器人
    - 电报机器人
    - 电报游戏搭建
    - 彩票游戏
    - 区块链
---
Telegram，作为一款全球领先的即时通讯应用，目前拥有超过9.5亿的月活跃用户，这一庞大的用户基数为Telegram MiniApps提供了无与伦比的市场潜力。本文将探讨如何将MiniApps集成到telegram，为telegram用户提供服务的开发过程。 Telegram MiniApps凭借其庞大的用户基础、高集成度、良好的用户使用习惯、低推广门槛以及卓越的兼容性，为开发者和企业提供了一个极具吸引力的平台。这些优势不仅有助于MiniApps的快速推广和普及，也为用户带来了更加丰富和便捷的移动体验。随着Telegram用户的持续增长和MiniApps功能的不断丰富，我们可以预见，Telegram MiniApps将在未来的移动应用市场中扮演越来越重要的角色
Telegram MiniApps的优势，包括其与用户的高集成度、良好的用户使用习惯、低推广门槛以及卓越的兼容性。

# Telegram MiniApps：利用庞大用户群和高度集成的优势
#### 庞大的用户基础
Telegram的9.5亿月活跃用户群体是其最显著的优势之一。这一庞大的用户基础为MiniApps提供了一个巨大的潜在市场，使得开发者和企业能够触及全球各地的用户。无论是小型创业公司还是大型企业，都能够利用Telegram的广泛用户群来推广自己的MiniApps，实现快速增长。

#### 高集成度
Telegram MiniApps与Telegram平台的高集成度是其另一大优势。用户可以在不离开聊天界面的情况下，直接访问和使用MiniApps，这种无缝的体验大大提升了用户的便利性和应用的可访问性。集成度高意味着用户无需在多个应用间切换，从而提高了用户粘性和应用的使用频率。

#### 良好的用户使用习惯
Telegram的用户已经习惯了在平台上进行各种活动，包括聊天、分享文件、参与群组讨论等。MiniApps的引入进一步丰富了用户的使用场景，使得用户可以在Telegram上完成更多任务，如在线购物、预订服务、参与游戏等。这种良好的用户使用习惯为MiniApps的推广和使用提供了有利条件。

#### 低推广门槛
由于Telegram MiniApps可以直接在聊天界面中使用，这大大降低了用户的尝试成本和推广门槛。用户无需下载额外的应用或访问外部网站，即可体验MiniApps提供的功能和服务。这种低门槛的推广方式有助于吸引更多的用户尝试和使用MiniApps，从而加速应用的普及和增长。

#### 卓越的兼容性
Telegram MiniApps支持跨平台运行，无论是在iOS、Android还是桌面客户端，用户都能享受到一致的体验。这种跨平台兼容性确保了MiniApps能够覆盖更广泛的用户群体，同时也减少了开发者在不同平台上进行适配的工作量。

# telegram 机器人创建流程
- 在telegram中搜索 BotFather 或者 点击  [创建机器人](https://t.me/BotFather  "队长游戏-创建机器人教程")。 即可申请创建，完全免费，即开即用，非常方便 
- 具体图文教程可参考本篇文章  [队长游戏-创建机器人教程](https://digilifetech.github.io/2024/07/10/%E5%A6%82%E4%BD%95%E4%BB%8E%E9%9B%B6%E5%BC%80%E5%A7%8B%E6%90%AD%E5%BB%BA%E7%94%B5%E6%8A%A5%E6%9C%BA%E5%99%A8%E4%BA%BA/  "队长游戏-创建机器人教程")

# 电报游戏机器人创建(telegram game bot)
- 已经申请了telegram bot之后，将bot转为game bot，在BotFather对话中，输入/newgame，如下图，根据BotFather引导来填写信息，提示后 选择 OK 按钮
    ![create new game](./img/8-30-newgame.png "创建new game")
- 机器人会提示有一些用户协议要求，选择Accept
    ![create new game](./img/8-30-accept.png "Botfather 引导填写内容")
- 之后机器人会提示要求选择一个机器人的username，这里用我们创建的telegram bot来做为telegram miniApps 游戏服务机器人
    ![create new game](./img/8-30-setname.png "Botfather 引导填写内容")
- 接下来设置这个game的名称，比如这里我们起名：乐透彩票
    ![create new game](./img/8-30-setnickname.png "Botfather 引导填写内容")
- 接下来需要输入对这个游戏机器人的描述，可以输入游戏的说明、游戏规则等,比如输入：智能合约彩票telegram MiniApps，公平公正，结果可验证，采用第三方chainlink VRF链上随机算法，结果不可更改。然后是要求上传一张图片，可以做一张效果图上传。
    ![create new game](./img/8-30-description.png "Botfather 引导填写内容")
- 接下来设置GIF图片，这个是在用户打开机器人的时候展示的，可以先跳过。选择一个短名称，比如我们填写：lotto。此时就已经创建成功，可以输入/mygames 来查看详细信息
    ![create new game](./img/8-30-shortname.png "Botfather 引导填写内容")

至此，telegram game bot已经创建完毕。接下来就是对接bot api和游戏逻辑。

# telegram bot api 对接 MiniApps 实现游戏数据互通
#### 开发语言的选择
开发电报机器人，可以选择的语言/框架有很多，比如node.js、python、php、java，Ruby等。考虑到开发速度来说、库的易用性等综合条件，选择python作为开发语言
#### 开发库的选择
telegram 的api比较原始，使用起来太多细节需要自己来处理，比较繁琐，因此可以选择一些封装好的SDK。选择了python作为开发语言，python对应的telegram api的sdk比较流行的有pyrogram、telethon等，这两个库都是基于TDLib的api功能比较强大，基本可以实现telegram客户端的所有功能。pyrogram的api封装的比telethon更易用一点，因此这里我们选择pyrogram。有喜欢telethon的也是一样的。
#### 安装相关开发库
pip install pyrogram django

安装后用django-admin 创建项目。
#### 使用pyrogram实现给django api 传参登录。代码如下：
    ```
    from pyrogram import Client
    import requests

    # 替换为你的 API ID 和 API Hash
    api_id = "YOUR_API_ID"
    api_hash = "YOUR_API_HASH"

    # 创建 Pyrogram 客户端
    app = Client("my_account", api_id=api_id, api_hash=api_hash)

    # 启动客户端并登录
    with app:
        # 获取当前用户信息
        me = app.get_me()
        print(f"Logged in as {me.first_name}")

        # 准备要传递给 Django API 的数据
        data = {
            "user_id": me.id,
            "first_name": me.first_name,
            "last_name": me.last_name,
            "username": me.username
        }

        # 发送 POST 请求到 Django API
        response = requests.post("http://your-django-api-url/login/", json=data)
        print(response.json())

    ```

django api 处理登录的逻辑，实现telegram 用户自动登录MiniApps 游戏。
    ```
    from django.http import JsonResponse
    from django.views.decorators.csrf import csrf_exempt
    import json

    @csrf_exempt
    def login(request):
        if request.method == "POST":
            data = json.loads(request.body)
            user_id = data.get("user_id")
            first_name = data.get("first_name")
            last_name = data.get("last_name")
            username = data.get("username")

            # 处理登录逻辑，例如创建或更新用户信息
            # ...

            return JsonResponse({"status": "success", "message": "User logged in successfully"})
        return JsonResponse({"status": "error", "message": "Invalid request method"})

    ```

实现用户打开机器人后，自动展示登录游戏、打开MiniApps的功能。
    ```
    from pyrogram import Client, filters
    from pyrogram.types import InlineKeyboardMarkup, InlineKeyboardButton

    # 替换为你的 API ID 和 API Hash
    api_id = "YOUR_API_ID"
    api_hash = "YOUR_API_HASH"

    app = Client("my_account", api_id=api_id, api_hash=api_hash)

    @app.on_message(filters.command("start"))
    async def start(client, message):
        # 创建一个带有 URL 按钮的键盘
        keyboard = InlineKeyboardMarkup(
            [
                [InlineKeyboardButton("🐯开始彩票游戏", web_app=WebAppInfo(url="https://lottogame.com?tgid"+message.from_user.id))]
            ]
        )
        await message.reply("公平公正，无法更改结果的区块链彩票游戏", reply_markup=keyboard)

    app.run()

    ```
 
 实现自动登录后，即可获取用户的分数等信息，开始游戏。

# 总结
以上介绍了telegram game bot(电报游戏机器人) 的申请过程，以彩票游戏为例子，实现电报机器人 对接 telegram MiniApps的方法。
根据此流程可以申请一个新的电报机器人用来搭建到群内做红包扫雷机器人、骰子机器人、pc28机器人、以及最近比较流行的TON 游戏机器人。

联系官方客服可以查看更多游戏试玩：[队长游戏产品列表](https://t.me/captainGameBot  "队长游戏产品列表，查看更多产品")
