# 常见的Google广告授权操作

<img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosProfiling-bro.png" alt="Profiling-bro" style="zoom:25%;" />

###### 前言

> 不知道各位在团队日常协作中，是否有有碰到以下问题：
>
> - 新Google广告授权给其他同事；
> - Google Analytics「后简称GA」授权给新加入业务线的同事；
> - Google Merchant Center「后简称GMC」新增操作用户；
> - Google Tag Manager「后简称GTM」授权给技术同事增加某个业务监控代码；
> - Google广告账户与GMC关联设置
> - Google广告账户与GA关联、GA转化数据导入Google广告账户；
>
> 各位在运营Google电商实际业务过程中，肯定碰到以上一个或多个与权限相关的问题，那么本篇文章将这些常见权限问题整合到本篇文章中。



##### 一、Google广告账户的授权操作

> 谷歌广告账户申请可以从自己MCC直接创建，创建之后让归属的一代绑定Billing支付，并设定额度「Budget amount」即可使用。**申请账户可以是自己或者代理商，绑定支付方式必须是归属的一代。**

![image-20210720102218327](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720102218327.png)

> 账户开设并充值好之后，就需要把广告账户授权给实际广告投放的小伙伴了，那具体如何授权呢？可参考下面步骤：

1. Tools & Settings >>> Access and security;![image-20210720102922792](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720102922792.png)
2. Add;![image-20210720103119352](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720103119352.png)

3. 输入受邀人的Gmail邮箱，并选择分配的权限，点击发送邀请；![image-20210720142934054](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720142934054.png)

4. 受邀请用户登录其Gmail邮箱，即可收到一封类似于如下截图的邮件，点击接受即可跳转到广告账户后台；![image-20210720103722151](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720103722151.png)

5. 如果你要取消对某个账户的邀请，或移除某个用户的权限，如下截图操作即可；![image-20210720104340032](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720104340032.png)





##### 二、GA账户的授权操作：

> GA现在有GA3和GA4，这里主要以电商较为习惯使用的GA3为例，GA作为一个统计分析网站流量的第三方工具，可以让大直老板，下直业务线的小伙伴清晰地观测到我们网站的流量来源和转化等信息。那GA如何邀请小伙伴一起工作呢？

1. Admin >>> Account Access Management， Add;![image-20210720111034590](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720111034590.png)

2. 输入受邀请用户的邮箱，并选择分配的GA权限，点击添加；![image-20210720111239294](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720111239294.png)

3. 权限移除，也非常简单；![image-20210720111341845](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720111341845.png)

> GA权限非常简单，授权和移除授权都非常清晰简单。



##### 三、GMC的授权操作

> 涉及到GMC的客户，基本都是电商客户。电商投放谷歌广告，购物广告是必不可少的广告类型，而投放购物广告离不开GMC，GMC的操作这里不做详述，仅简单过一下授权相关事宜。

1. Settings >>> Account Access；![image-20210720114509179](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720114509179.png)

2. 点击Add User，并输入受邀用户的邮箱；![image-20210720114743893](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720114743893.png)





##### 四、GTM的授权操作

> GTM使用一种Google开发的容器技术，方便我们安装对接各个流量渠道的广告监控代码，包括Google自家的Google Ads、 Google Analytics、 Google Remarketing等等，以及诸如Bing、Criteo、Twitter、LinkedIn等第三方媒介代码。而且都是比较傻瓜式的方式即可实现代码对接；

1. 在Home界面，点击你需要授权的容器；![image-20210720130504311](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720130504311.png)

2. User Management >>>Add Users；![image-20210720131836561](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720131836561.png)

3. 输入受邀用户邮箱，并选择权限设置，发送邀请；![image-20210720132125256](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720132125256.png)

4. See all>>>更严格的权限设置；![image-20210720132228186](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720132228186.png)

##### 五、Google Ads与GMC关联（链接）

> Google Ads为啥要和GMC关联？你要做购物广告，购物广告是基于Feed，Feed是托管在GMC中的，所以你必须链接Google Ads和GMC之后才能做谷歌的购物广告。这就是为啥要操作Google Ads和GMC。那如何关联呢？

1. 在Google Ads账户后台，`Tools & Settings>>>Linked Account；`![image-20210720134153486](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720134153486.png)

2. 在跳转的新界面，选择Google Merchant Center，点击`Details`；![image-20210720134405228](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720134405228.png)

3. 在下面界面选择Link  **Google Ads后台需要用有对应GMC权限的个人账号，否则无法Link；一个Google Ads有且只能Link一个GMC** ；![image-20210720134746650](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720134746650.png)



##### 六、Google Ads 与 GA关联（链接）

> 和上面关联Google Ads和GMC类似，在Linked Accounts界面，选择Google Analytics(UA)，Link对应的Analytics Property即可；

![image-20210720140304473](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720140304473.png)



##### 七、Google GA数据回传到Google Ads中；

> 由于GA和Google Ads对于转化的跟踪逻辑其实是不同的，所以两边记录到的转化数据不一致是必然存在的，减少两边转化跟踪的统计差异，主要可以从以下几个方面入手：
>
> - 两边均采用Last Click作为归因；
> - 把GA统计到的通过广告带来的转化回传到Google Ads账户中
>
> 那么第二个措施，如何把GA统计到的从Google广告过去的转化回传到Google Ads广告账户中呢？

1. 在Google广告账户后台，Tools & Settings >>> Conversions；![image-20210720141123910](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720141123910.png)

2. 点击`➕`；![image-20210720141446237](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720141446237.png)

3. 选择Import >>> Google Analytics (UA)，并继续；![image-20210720141616065](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720141616065.png)

4. 在弹出的窗口中，选择你需要导入和跟踪的转化数据；
   - 注意事项：
     - 电商类，非购买转化，推荐不用计入Conversions中，Conversions中只包含直接的购买转化；
     - 所有转化计算次数，推荐在Cookie有效期内只算一次，**但针对购买转化，统计每一次转化**；

<img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosOnline%20document-bro.png" alt="Online document-bro" style="zoom:25%;" />

> 关于Google电商广告投放过程中，日常接触到的涉及权限授权和管理的几个常见的操作，以上已全部图文简述完毕。
