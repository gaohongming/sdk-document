## 小米SDK配置说明

 ###  一.接入前的准备

  1. 在小米开发者网站 http://dev.xiaomi.com，注册账号并创建应用。

  2. 获取游戏所需的参数：AppID、AppKey、AppSecret。

  ![](http://docs.mztgame.com/files/assets/img/mi-online1.jpg)

  3. 支付回调地址配置：
    点击上图红框进去配置支付回调地址
    点击配置

  ![](http://docs.mztgame.com/files/assets/img/mi-online2.jpg)

  选择“按金额付费”

  ![](http://docs.mztgame.com/files/assets/img/mi-online3.jpg)

  点击下一步，配置回调地址。小米的回调地址为：

### 二.注意事项

  1.  包名 + ** `.mi ` ** ，并且必须与**小米后台申请的包名一致**。
  2.  在小米开发者后台申请参数后，一定要配置应用内支付。
  3.  小米的支付金额必须为大于1元的整数，小于1元支付时会提示“创建订单失败”。小米的银行卡充值额度为50—2000元，最低50元。
  4. 小米有切换账号功能,可以联系小米技术人员配置.

### 三.常见问题

   1. 登录时提示：验证token失败，请尝试重新登录。
    先清空一下小米游戏安全插件的数据，然后联网重新试试，这个问题多数是由于网络问题引起的。

   2. 进入游戏时，登陆界面没有出现，显示错误：errcode[1515] errmsg=[null]

        1. 请确认参数是否正确。

        2. 请确认包名是否与开发者站配置的一致(包名必须以.mi结尾)。

        3. 在小米开发者后台配置应用内支付。
   3. 支付成功了,为什么游戏服务器没有看到支付成功的交易记录？

       1. 请先确认订单是否支付成功，因为只有用户支付成功的订单才会回调通知游戏。

       2. 请确认小米的运营人员是否正确配置了支付通知地址。

       3. 调用小米的登陆界面登陆成功之后， onCallbackEvent中收不到任何回调？
              请确认配置了应用内支付。

       4. 点击登录，提示安装小米插件时，游戏闪退；或点击返回键取消登录时，游戏挂掉，怎么办？
               在登录失败回调onLoginFailed里面不能加入Toast提示框和pop框。

   4. 小米登录，支付以及其他问题。
      小米遇到问题可以先打印一下小米的log，tag为MiGameSDK。看到错误提示之后和小米应用内支付错误代码比对一下，可以自己检查出问题。小米错误代码网址：http://dev.xiaomi.com/doc/p=2784/      