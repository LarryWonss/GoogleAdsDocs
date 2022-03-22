# 巧用UTM参数精准跟踪多流量渠道成效 

<small>精细化运营策略之【订单来源跟踪】</small>

##### 1、话题引入

###### 1.1、老板视角：

> 对于独立站的卖家，需要商家自己引流推广，不管是免费的SEO流量，还是付费的广告方式。尤其当网站前期较大比重的流量依靠付费广告时，对于营销支出以及对应的产出的追踪是非常重要的。这个时候，搭建一套科学的流量成效跟踪系统对于从宏观层面把控整体独立站项目营销预算分配、人力资源分配等方面，就显得尤为重要。这套系统，可以清晰的知道每个流量渠道，以及该流量渠道的投入产出比（包括广告花费、订单数量、订单总销售额等）。特别是当营销渠道增多时，Google, Facebook, Bing , SEO, EDM等， 那么就必须清晰地从数据层面进行量化分析每个渠道的成效情况。如果我们不使用UTM参数这套系统，就无法准确进行分析。



###### 1.2、业务视角

> 随着目前DTC精品独立站的卖家越来越多，很多卖家在做网站推广引流的时候，首选的Facebook 和 Google渠道肯定是采用的，当他们需要更多流量的时候，他们可能会加入诸如Bing、TikTok、Snapchat、Twitter等等更多渠道，随着网站流量的沉淀，他们可能还会启用再营销Criteo进行引流。这么多流量平台，怎么衡量我们的广告花费带来的实际成效呢？ 当然，广告平台本身肯定是可以看到其成效呢（Cost/Click/Conversion/Conversion Value等维度数据）。
>
> **举个例子：**通常情况下，一个消费者，也就是一个用户，他可能在浏览Facebook信息流的时候，看到了我们的产品，并且进入到我们网站进行浏览了页面，但最后没有购买。过了几个小时或者几天，他又想起来，需要买这类产品时，他首先在Google的搜索框中输入了产品名字，且刚好我们的网站或产品出现了，这个用户点击了我们的链接，并最后完成了购买。这个时候，怎么归因这个订单？ 首先，从广告渠道来说，Facebook肯定会归因为其渠道带来的订单成交，因为其转化窗口通常默认情况下是【28天（首次）点击和1天浏览】，这个订单转化满足这个条件，所以Facebook会归为其渠道带来的成效；从Google广告渠道的视角分析，通常情况下设置转化归因为【30天（末次）点击和1天浏览】，最后这个用户也是通过点击谷歌广告完成了转化，满足Google的归因模型，Google计入为Google的成效。
>
> **如果从广告媒介的角度综合分析，我们广告后台一共记录到2个订单，但是从我们网站后台的视角来看，我们只获得了一个订单，这个时候核算广告平台的ROAS和网站真实的ROAS，算出来的数据就会比较大的差异。这里面就涉及到一个问题，怎么比较合理地去核算广告渠道的实际广告成效？**
>
> ——这个时候，我们就需要制定一套比较符合逻辑的订单统计与归因模型。GA目前也是在用这套统计逻辑的，就是使用utm参数进行广告成效跟踪。



##### 2、UTM介绍

###### 2.1、UTM是什么

> 维基百科上是这么解释UTM的：
>
> **Urchin Tracking Module** (**UTM**) **parameters** are five variants of URL parametersused by marketers to track the effectiveness of online marketing campaigns across traffic sources and publishing media. They were introduced by [Google Analytics](https://en.wikipedia.org/wiki/Google_Analytics)' predecessor [Urchin](https://en.wikipedia.org/wiki/Urchin_(software)) and, consequently, are supported out-of-the-box by Google Analytics. The UTM parameters in a URL identify the campaign that refers traffic to a specific website, and attributes the browser's website session and the sessions after that until the campaign attribution window expires to it. The parameters can be parsed by analytics tools and used to populate reports.
>
> This example URL has the UTM parameters highlighted:
>
> **https://www.example.com/page?utm_content=buffercf3b2&utm_medium=social&utm_source=facebook.com&utm_campaign=buffer**



###### 2.2、UTM中的5个字段

> UTM参数一共有5个字段，可以按照任意顺序使用：

|  Parameter   |                           Purpose                            |                       Example                        |
| :----------: | :----------------------------------------------------------: | :--------------------------------------------------: |
|  utm_source  | Identifies which site sent the traffic, and is a required parameter. |                utm_source=**google**                 |
|  utm_medium  | Identifies what type of link was used, such as [cost per click](https://en.wikipedia.org/wiki/Cost_per_click) or email. |                  utm_medium=**cpc**                  |
| utm_campaign | Identifies a specific product promotion or strategic campaign. |             utm_campaign=**spring_sale**             |
|   utm_term   |                   Identifies search terms.                   |              utm_term=**running+shoes**              |
| utm_content  | Identifies what specifically was clicked to bring the user to the site, such as a [banner ad](https://en.wikipedia.org/wiki/Banner_ad) or a [text link](https://en.wikipedia.org/wiki/Hyperlink). It is often used for [A/B testing](https://en.wikipedia.org/wiki/A/B_testing) and [content-targeted ads](https://en.wikipedia.org/wiki/Contextual_advertising). | utm_content=**logolink** or utm_content=**textlink** |



##### 3、UTM的使用

###### 3.1、在付费广告渠道的使用：

1. Facebook渠道：

   - 如何跟踪主页贴文的成效（内容营销的成效如何借助UTM参数进行量化）：

     > 如果营销主管要衡量手下一位专职做Content Marketing人员在运营Facebook Page的效果时，怎么可以比较科学且准确地借助UTM进行跟踪呢？

     ![image-20210920131600772](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920131600772.png)

     图中这条短链就使用了我们上面提到的UTM参数。我们看到的是一条很短的链接，实际这条链接全链接是：

     **https://www.cupshe.com/products/blue-white-and-black-striped-bikini?utm_source=fb&utm_medium=post&utm_campaign=sns_0919AC11425M&url_from=sns_0919AC11425M&fbclid=IwAR3BAC2oXJFLbdO9THLsJIRwnBt-_LwDtUCt4PvUCjIYArm9--nIoDq_EsY**我们来分析一下这串链接：

     - utm_source=fb 定义这些数据来源于fb这个大渠道
     - utm_medium=post 定义这是来源于Facebook Post贴文的数据
     - utm_campaign=sns_0919AC11425M定义了系列 为sns的流量
     - Url_from=sns 可能是内部定义，其中0919代表9月19号
     - fbclid=xxx 是Facebook系统自动添加的Facebook内部的标识

     那么经过这么一长串UTM参数定义后，商家在GA后台或者其网站后台统计贴文的效果时就非常有帮助，可以轻松地统计到这条贴文带来的点击数、订单数和销售额数据；

     

   - 如何跟踪广告的成效（付费广告的成效如何借助UTM参数进行量化）：

     > 我们上面通过Facebook贴文的这个实际案例了解到，原来UTM参数对于统计广告成效这么有帮助，那么我们怎么使用其在付费广告渠道上进行跟踪统计呢？首先来聊聊Facebook的Ads Manager后台怎么使用UTM参数辅助跟踪。

     <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920133219486.png" alt="image-20210920133219486" style="zoom:50%;" />

     上面截图为Ads Manager后台 Ads层级截图，其中有个板块内容是Tracking，Tracking下面允许我们选择Website Events和Offline Events，其中Offline Events中有个URL Parameters，这个参数是Optional选项，我们可填写，可不填写。在输入框之后，还有个Build a URL Parameter的按钮，我们点击这个超链接，会弹出以下界面：

     <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920133519683.png" alt="image-20210920133519683" style="zoom:33%;" />

     在这个界面，我们可以配合我们内部的UTM跟踪系统，设置相应的参数，以达到我们的跟踪目的，下面截图是我自己常用的设置方式：
     <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920133920091.png" alt="image-20210920133920091" style="zoom:33%;" />
     当然，在后续的广告中，我们也可以直接就复制黏贴Parameter Preview展示的跟踪代码，没必要每条广告都用Build a URL Parameter这个超链按钮生成。
     
     ```
     utm_source={{site_source_name}}&utm_medium=cpc&utm_campaign={{campaign.name}}&utm_content={{ad.name}}&placement={{placement}}
     ```

2. Google渠道：

   > Google广告账户层级有个Auto-tagging的设置，如果我们打开这个设置，且我们在实际制作广告的时候，没有手动设置UTM参数，那么系统就会自动使用其系统内的gclid字段，具体可以见下图详细说明。

   <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920134559124.png" alt="image-20210920134559124" style="zoom:50%;" />

   > 但是通常我们都开启Auto-tagging辅助GA统计，同时在实际制作广告的过程中，在广告资产「广告系列、广告组、广告、Extension等」中设置好对应的需要跟踪的UTM参数；

   - 在广告系列设置UTM参数：

     <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920134956265.png" alt="image-20210920134956265" style="zoom:50%;" />

   - 在广告组中设置UTM参数：

     <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920135044552.png" alt="image-20210920135044552" style="zoom:50%;" />

   - 在广告中设置UTM参数：

     <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920135148241.png" alt="image-20210920135148241" style="zoom:50%;" />

   - 在Extension中设置参数：

     <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920135248378.png" alt="image-20210920135248378" style="zoom:50%;" />

   

3. Bing渠道：

   > Bing作为一个搜索渠道，在欧美，尤其是北美地区拥有不少中高收入的年龄稍长的用户群体，其广告也是搜索广告和购物广告为主，和Google广告基本类似。Google广告优化师基本可以无缝上手，其当然也支持UTM参数这套公用跟踪系统。那如何在Bing后台进行设置UTM参数呢?

   **Auto-tagging 可开，可不开，具体有啥影响，可以点击Auto-tagging fo Click ID右边的小问号。**

   - Auto-tagging of Click ID:

       <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920140317823.png" alt="image-20210920140317823" style="zoom:50%;" />

   - 广告系列增加UTM参数设置：
       <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920140456251.png" alt="image-20210920140456251" style="zoom:50%;" />

   - 广告组增加UTM参数设置：
       <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920140552573.png" alt="image-20210920140552573" style="zoom:50%;" />

   - 广告层级增加UTM参数设置：
       <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920140755521.png" alt="image-20210920140755521" style="zoom:50%;" />

   - 购物广告增加UTM参数设置：在广告系列或者广告组层级设置UTM即可。

     

4. Criteo渠道：

   > Criteo作为一个再营销平台，目前来说，应该是全球效果最稳定，技术实力靠前的一个广告分发平台，其平台本身没有流量，Criteo主要使用技术和算法实现我们的广告精准再营销。目前该平台对于网站有一定的流量基础要求。这个平台也是支持UTM参数设置的。

   入口为：Campaigns->>>Ad Sets---**Ads Tracking**

   <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920141424087.png" alt="image-20210920141424087" style="zoom: 33%;" />

5. 渠道总结

   > 以上我只是介绍了我日常工作中常接触到的几个流量媒介，其实UTM参数这套系统，适用于整个互联网任何有设计到链接点击和成效跟踪的系统中。当然这也不是一套完美的系统，但是对于品牌电商出海独立站来说，足够用且非常有必要。其可以大大方便我们营销人员实时跟踪我们的广告成效数据。就比如我目前运营的一个项目Case，其使用Shopyy建站，Shopyy这个Saas已经支持UTM这套统计逻辑，但是目前只有两个字段，utm_source和utm_medium。

   <img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920142144282.png" alt="image-20210920142144282" style="zoom:50%;" /><img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210920142421209.png" alt="image-20210920142421209" style="zoom: 33%;" />