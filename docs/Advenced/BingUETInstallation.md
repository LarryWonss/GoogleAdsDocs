# Bing广告代码对接方法整理

### 通用方法：

#### 一、基础代码（全局安装）：

以下js代码网站所有页面均需要安装

```js
<script>
(function(w,d,t,r,u){var f,n,i;w[u]=w[u]||[],f=function(){var o={ti:"56274642"};o.q=w[u],w[u]=new UET(o),w[u].push("pageLoad")},n=d.createElement(t),n.src=r,n.async=1,n.onload=n.onreadystatechange=function(){var s=this.readyState;s&&s!=="loaded"&&s!=="complete"||(f(),n.onload=n.onreadystatechange=null)},i=d.getElementsByTagName(t)[0],i.parentNode.insertBefore(n,i)})(window,document,"script","//bat.bing.com/bat.js","uetq");
</script>
```



#### 二、事件代码（页面安装）

上面已经安装了全局代码，所以只需要在产品页面下面填下以下额外代码，注意需要根据实际的字段修改以下代码中的**REPLACE_WITH_EVENT_XX**字段

- 以下为**事件代码模板**

```js
<script>
window.uetq = window.uetq || [];
window.uetq.push('event', 'REPLACE_WITH_EVENT_ACTION', 
                 {'event_category': 'REPLACE_WITH_EVENT_CATEGORY',
                  'event_label': 'REPLACE_WITH_EVENT_LABEL', 
                  'event_value': 'REPLACE_WITH_EVENT_VALUE',
                  'revenue_value': 'REPLACE_WITH_REVENUE_VALUE', 
                  'currency': 'REPLACE_WITH_CURRENCY_CODE'
                 }
                );
</script>
```

**Category**: The category of the event you want to track.  Let's say you want to track downloads of a document on a page of your  site. For this example, the category could be "downloads".

**Action**: The type of user interaction you want to track. For our example, "downloadbuttonclick".

**Label**: The name of the element that caused the action. For our example, "document05".

**Value**: A numerical value associated with that event. For our example, the number of pages in the document: "4".
  					  The event value can be any value from 0 to 9999999 to 3 decimal places. 

##### 2.1 加购页面

```javascript
<script>
window.uetq = window.uetq || [];
window.uetq.push('event', 'add-to-cart',{});
</script>
```



##### 2.2 购买成功页面

```javascript
<script>
window.uetq = window.uetq || [];
window.uetq.push('event', 'purchase',
                 {'event_category': '',//可保留空值
                  'event_label': '', //可保留空值
                  'event_value': '',//可保留空值
                  'revenue_value': '',//填写每次购买成功的转化金额参数,填写每次加购的金额对应的参数
                  'currency': '';//货币参数代码,多币种站点统计转化金额需要，如果多重币种，还涉及到汇率兑换参数代码
                 }
                );
</script>
```



**注意事项：**具体的加购页面、结账页面、付款成功页面，本来就需要安装全局代码，广告后台要记录这些单独的事件，还需要分别在原来的全局代码基础之上，安装以上的事件代码，完整的代码应该是如下示例。

```js
<script>
(function(w,d,t,r,u){var f,n,i;w[u]=w[u]||[],f=function(){var o={ti:"56274642"};o.q=w[u],w[u]=new UET(o),w[u].push("pageLoad")},n=d.createElement(t),n.src=r,n.async=1,n.onload=n.onreadystatechange=function(){var s=this.readyState;s&&s!=="loaded"&&s!=="complete"||(f(),n.onload=n.onreadystatechange=null)},i=d.getElementsByTagName(t)[0],i.parentNode.insertBefore(n,i)})(window,document,"script","//bat.bing.com/bat.js","uetq");

window.uetq = window.uetq || [];
window.uetq.push('event', 'REPLACE_WITH_EVENT_ACTION', 
                 {'event_category': 'REPLACE_WITH_EVENT_CATEGORY', 
                  'event_label': 'REPLACE_WITH_EVENT_LABEL',
                  'event_value': 'REPLACE_WITH_EVENT_VALUE', 
                  'revenue_value': 'REPLACE_WITH_REVENUE_VALUE', 
                  'currency': 'REPLACE_WITH_CURRENCY_CODE'
                 }
                );

</script>
```

- event_name can be empty or any of the following: **add_payment_info, add_to_cart, add_to_wishlist, begin_checkout, checkout_progress, exception, generate_lead, login, page_view, purchase, refund, remove_from_cart, screen_view, search, select_content, set_checkout_option, share, sign_up, timing_complete, view_item, view_item_list, view_promotion, view_search_results)**

![image-20200813132237959](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgWzgFk1sUhDbuGMr.png)





### 附录

#### 一、Shopify店铺添加BING代码的方式【[官方文档](https://help.ads.microsoft.com/#apex/3/en/56901/0)】

> 近期Shopify卖家雨后春笋般出现，也越来越多的卖家们有投放Bing广告的投放需求，在投放广告之前如何对接Bing的UET监控代码呢？本篇就是为了解决大家这个疑问。

Shopify后台和Bing广告后台都登录上，同时在Bing广告后台设置好UET Tag，先生成好UET基础代码，基础代码如下图所示：

![image-20200904150951913](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgQbUzv9jwskx2ZBM.png)

- 复制出来的代码如下：

  ```javascript
  <script>(function(w,d,t,r,u){var f,n,i;w[u]=w[u]||[],f=function(){var o={ti:"17xxxx53"};o.q=w[u],w[u]=new UET(o),w[u].push("pageLoad")},n=d.createElement(t),n.src=r,n.async=1,n.onload=n.onreadystatechange=function(){var s=this.readyState;s&&s!=="loaded"&&s!=="complete"||(f(),n.onload=n.onreadystatechange=null)},i=d.getElementsByTagName(t)[0],i.parentNode.insertBefore(n,i)})(window,document,"script","//bat.bing.com/bat.js","uetq");</script>
  ```

##### 部署操作：

1. 在Shopify后台，点击`Online Store（应用商店）>>>Themes（模板）>>>Edit Code（编辑代码）`进入到后台模板代码编辑界面

   ![image-20200904170726070](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgaKWDHd95lz7LSPT.png)

2. 打开```theme.liquid```，把上面BING UET的基础代码复制到`<head>...</head>`之间，并保存该代码。如下所示：

   - 完整代码如下：

     ```javascript
     <script>
     (function(w,d,t,r,u){var f,n,i;w[u]=w[u]||[],f=function(){var o={ti:"17xxxx53(TagID)"};o.q=w[u],w[u]=new UET(o),w[u].push("pageLoad")},n=d.createElement(t),n.src=r,n.async=1,n.onload=n.onreadystatechange=function(){var s=this.readyState;s&&s!=="loaded"&&s!=="complete"||(f(),n.onload=n.onreadystatechange=null)},i=d.getElementsByTagName(t)[0],i.parentNode.insertBefore(n,i)})(window,document,"script","//bat.bing.com/bat.js","uetq");</script>
     ```

     ![image-20200904171030425](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgAdkclKED9LwYHVC.png)

3. 打开```Setting（设置）>>>Checkout（结账）```，在```Additional Scripts```黏贴下面代码并保存。

   - 如果想要Bing广告账户记录到的转化金额**排除税款和运费**，请使用以下代码：

     ```javascript
     {% if first_time_accessed %}  //防止重复触发，所以加入此判断
     <script>
        window.uetq = window.uetq || []; 
        window.uetq.push('event', 'purchase', //例如：此处定义为purchase事件，如果定义为purchase事件，Bing后台可使用event追踪
        						{'revenue_value': {{ subtotal_price | money_without_currency }}, 							'currency': '{{ shop.currency }}' 
            					}
        					); 
     </script>
     {% endif %}  //防止重复触发结束代码
     ```

   - 如果想要Bing广告账户记录到的转化金额**包含税款和运费**，请使用以下代码：

     ```javascript
     {% if first_time_accessed %}  //防止重复触发，所以加入此判断
     <script>
        window.uetq = window.uetq || []; 
        window.uetq.push('event', 'purchase',  //例如：此处定义为purchase事件，如果定义为purchase事件，BING后台可使用event追踪
                  			{ 'revenue_value': {{ total_price | money_without_currency }}, 
                        		  'currency': '{{ shop.currency }}' 
                  			}
        					); 
     </script>
     {% endif %}  //防止重复触发结束代码
     ```

   ***注意：***

   - 如果客户网站使用的是带逗号分隔的货币数值，关于revenue_value需要进行微调，代码如下：

     ```javascript
     {'revenue_value': '{{ checkout.total_price | money_without_currency | remove: '.' | remove: ',' | divided_by: 100 }}'
     ```

   - Shoplazza建站方式和Shopify关于Revenue参数一样。![image-20201224101115042](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgcQosKGeP3vIFL17.png)

   

   

4. 保存。



##### Conversion Goal设置

1. UET TAG ID申请生成基础代码，前面第一步已经提到了，本处略。

2. 点击Conversion Goal >>> Create Conversion Goal。

3. 根据需要创建并监控的事件名称，自定义转化事件的Name（通常只需要监控AddToCart和Purchase）

   - 通过Destination URL的方式触发监控代码
     - Purchase事件触发的URL为：xxx.com/thank_you；AddToCart事件触发的URL为：xxx.com/cart![image-20200904173118330](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgoHd38kSPqB2pZsw.png)
   - 通过Event的方式跟踪转化事件；
     - 创建跟踪事件，选择Event跟踪，Event Action选择为代码中对应的事件名，可能是Purchase，也可以是其他自定义的事件；![image-20201224102030508](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgm6qns8Kwl1YSI7P.png)

   

   

4. 建议AddToCart和Purchase两个事件都分别设置一下

     

#### 二、Shopyy建站方式添加BING代码的方式：

##### 代码部署：

Shopyy后台可以直接通过添加UET TAG ID的方式，简单且方便的安装好全局基础代码也就是下面这一段。

入口为：**配置>>>基础配置>>>广告追踪**， 在此处填写好UET TAG ID，提交保存即可。

- ![image-20200903154834157](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgsdNMuDpK1YgV5wX.png)
- ![image-20200903154941822](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgMfhgU3SLiG4R8oC.png)

##### Conversion Goal设置：

> 推荐使用event事件进行追踪，上周我和Shopyy的COO直接就UET对接进行了探讨，目前SHOPYY定义了如下事件：
>
> `page_view`, `begin_checkout`, `search`, `view_content`, `sign_up`, `login` , `add_to_cart`, `add_to_wishlist`，`purchase`
>
> 当然，也可以使用使用追踪URL的方式进行追踪，URL特征如下：
>
> - 加购页面：` xxx.com/shopcart.html`
> - 支付成功页面：
>   - PC端：` xxx.com/h-order-success.html`
>   - M端：` /m-order-success.html`

关于Shopyy其他页面特征：

- Forget Password：`/h-user-forgetPassword.html`
- My Orders: `/h-account-orderList.html`
- Tracking Order：`/h-account-trackingOrder.html`
- My Account：`/h-account-index.html`
- Register：`/h-user-LoginOrRegister.html`
- Feedback：`/h-module-feedback.html`
- 支付成功链接
  - PC端：      ` /h-order-success.html`
  - 手机端：   `/m-order-success.html`

- 加购链接： `/shopcart.html`
- 所有产品：`` /Products/list-r1.html   ``
- 预售： `/Presale/list-r1.html`
- 可以列出所有的活动：   `/Offer/list-r1.html`
- 站点地图： `/h-sitemap-pc.html`





#### 三、UEESHOP建站方式添加BING代码的方式：

自定义代码入口：**应用>>>应用商店>>>自定义代码**，安装并启用，然后进入到代码自定义界面。

- ![image-20200903155801797](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgGJL4AYtHgkuhDPM.png)

- ![image-20200903160022066](C:\Users\Jackeroo Liu\AppData\Roaming\Typora\typora-user-images\image-20200903160022066.png)

- ![](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgyS9bX8KWHGmUvPc.png)

通过上面的截图，我们发现，UEESHOP只能在网站所有页面和的head或者body部分添加自定义代码，而BING的代码分为两部分，基础代码和转化代码，基础代码需要网站所有页面添加，但是转化代码只需要添加到加购成功或者支付成功的页面。那么UEESHOP就只能添加基础代码了。**鉴于此，推荐UEESHOP建站客户使用GTM管理BING代码。**







#### 四、Shoplazza(店匠)建站方式添加BING代码的方式：

##### 部署操作：

Shoplazza对于加代码的这件事情，做的比较细，具体可以从下面的页面中发现：

- **基础代码：**

  - 入口：```应用市场>>>自定义代码：```

  - 代码设置：PC端和手机端，触发页面为全部，代码位置为顶部

  - 代码如下：

    ```javascript
    <script>
    (function(w,d,t,r,u){var f,n,i;w[u]=w[u]||[],f=function(){var o={ti:"56274642"};o.q=w[u],w[u]=new UET(o),w[u].push("pageLoad")},n=d.createElement(t),n.src=r,n.async=1,n.onload=n.onreadystatechange=function(){var s=this.readyState;s&&s!=="loaded"&&s!=="complete"||(f(),n.onload=n.onreadystatechange=null)},i=d.getElementsByTagName(t)[0],i.parentNode.insertBefore(n,i)})(window,document,"script","//bat.bing.com/bat.js","uetq");
    </script>
    
    //记得更换对应TAG ID即可
    ```

    ![image-20200904115605936](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgmvwj4U73C6czOdN.png)

    

- **事件代码——加购事件**

  - 代码设置：触发页面设置为购物车页面，代码位置在顶部

  - 代码如下：

    ```javascript
    <script>
    window.uetq = window.uetq || [];
    window.uetq.push('event', 'add_to_cart',{});
    </script>
    ```

    ![image-20200904120312904](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgqgt1GENQUlr2jRI.png)

- **事件代码——购买事件**

- 代码设置：触发页面设置为Checkout页面，代码位置在顶部

- 代码如下：

  - 如果想要Bing广告账户记录到的转化金额**排除税款和运费**，请使用以下代码：

    ```javascript
    <script>
         window.uetq = window.uetq || []; 
         window.uetq.push('event', 'purchase', //例如：此处定义为purchase事件，如果定义为事件，Bing后台可使用event追踪
         						{'revenue_value': {{ subtotal_price | money_without_currency }}, 							'currency': '{{ shop.currency }}' 
             					}
         					); 
    </script>
    ```

    

  - 如果想要Bing广告账户记录到的转化金额**包含税款和运费**，请使用以下代码：

    ```javascript
    <script>
       window.uetq = window.uetq || []; 
       window.uetq.push('event', '',  //例如：此处定义为purchase事件，如果定义为事件，Bing后台可使用event追踪
                 			{ 'revenue_value': {{ total_price | money_without_currency }}, 
                       		  'currency': '{{ shop.currency }}' 
                 			}
       					); 
    </script>
    ```

    

##### Conversion Goal设置：

1. 和前面shopify 设置Conversion Goal类似，可以（**不推荐**）使用URL方式进行追踪，Shoplazza建站的URL特征为：

   - 加购页面：`xxx.com/cart/`
   - 支付成功页面：`xxx.com/thank_you`

2. 使用event事件进行跟踪：——**推荐，使用URL方式可能会跟踪不到转化事件和对应的转化价值**

   - 事件跟踪设置——**这里以购买事件为例**：![image-20201224102030508](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgm6qns8Kwl1YSI7P.png)

       

     ​    

#### 五、 xshoppy建站方式添加BING代码的方式

> 前段时间，徐老师已经对接过了，xshoppy安装Bing的UET代码只需要黏贴TAG ID即可。

具体步骤如下：

1. 获取BING TAG ID（步骤略）
2. 在xshoppy店铺后台黏贴TAG ID，路径为`店铺管理>>>追踪设置>>>Bing Ads UET标签`，保存即可。
3. Conversion Goal设置说明：
   - 查看产品详情页：URL跟踪，跟踪`/products`;
   - 加入购物车：事件跟踪，跟踪`add_to_cart`;
   - 订单支付成功：URL跟踪，跟踪`/thank_you`;

**xshoppy官方设置教程链接：https://help.xshoppy.com/new/#/article/detail/364140**





#### 六、BING Conversion Goal设置，推荐使用event事件跟踪，具体设置如下：

> 对于一些自建站客户来说，使用URL的方式追踪广告效果可能存在客户更新URL后，跟踪失效。为了避免此类事件的出现，对于跟送事件，推荐使用event事件进行跟踪。

1. 加购页面代码：

```javascript
<script>
(function(w,d,t,r,u){var f,n,i;w[u]=w[u]||[],f=function(){var o={ti:"56xxxx42"};o.q=w[u],w[u]=new UET(o),w[u].push("pageLoad")},n=d.createElement(t),n.src=r,n.async=1,n.onload=n.onreadystatechange=function(){var s=this.readyState;s&&s!=="loaded"&&s!=="complete"||(f(),n.onload=n.onreadystatechange=null)},i=d.getElementsByTagName(t)[0],i.parentNode.insertBefore(n,i)})(window,document,"script","//bat.bing.com/bat.js","uetq");

window.uetq = window.uetq || [];
window.uetq.push('event', 'add_to_cart', 
                 {}
                );
</script>
```

2. 支付成功页面代码：

```javascript
<script>
(function(w,d,t,r,u){var f,n,i;w[u]=w[u]||[],f=function(){var o={ti:"56xxxx42"};o.q=w[u],w[u]=new UET(o),w[u].push("pageLoad")},n=d.createElement(t),n.src=r,n.async=1,n.onload=n.onreadystatechange=function(){var s=this.readyState;s&&s!=="loaded"&&s!=="complete"||(f(),n.onload=n.onreadystatechange=null)},i=d.getElementsByTagName(t)[0],i.parentNode.insertBefore(n,i)})(window,document,"script","//bat.bing.com/bat.js","uetq");

window.uetq = window.uetq || [];
window.uetq.push('event', 'purchase', 
                 {'event_category': 'REPLACE_WITH_EVENT_CATEGORY', 
                  'event_label': 'REPLACE_WITH_EVENT_LABEL',
                  'event_value': 'REPLACE_WITH_EVENT_VALUE', 
                  'revenue_value': 'REPLACE_WITH_REVENUE_VALUE', 
                  'currency': 'REPLACE_WITH_CURRENCY_CODE'
                 }
                );

</script>
```

3. Conversion Goal设置：

- 加购追踪设置：![image-20200909171349085](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgcQMyu2If8CE63ls.png)

    

- 支付成功追踪设置：![](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgcQMyu2If8CE63ls.png)

    

**一个核心点：在事件代码中的`window.uetq.push('event', 'xxxxx'` 中，xxxxx要和conversion event设置的事件名字一样，即可。所有需要跟踪的事件，均可以使用类似的方式进行跟踪。**





**经过查询，关于国内各大建站工具与BING代码对接的信息如下：**

- 已有客户使用且有对接解决方案的平台有：shopify、xshopy(对接中)、ueeshop（GTM）、shopyy、shoplazza
- 用户较多但无成熟对接方案的建站平台有：wordpress、magento、zencart、bigcommerce、woocommerce、Sitebuilder、OpenCart；
- 接触但了解较少的平台有：shopage、imcart、Volusion、DIGOOD多谷等。
- BING官方有对接教程但国内无客户使用的平台有：WIX、



#### 六、More Information:

- [How do I create a UET tag?](https://help.ads.microsoft.com/#apex/3/en/56682/0)
- [How to track custom events with UET](https://help.ads.microsoft.com/#apex/3/en/help:app51208/1/en-US/#ext:ConversionGoals_Load)
- [Everything you need to know about setting up UET](https://help.ads.microsoft.com/#apex/3/en/56913/2-500)
- [Find out if my tag is working with UET Tag Helper](https://help.ads.microsoft.com/#apex/3/en/56775/2-500)
- [Set up UET tags using Google Tag Manager, Tealium, and other tag management systems](https://help.ads.microsoft.com/#apex/3/en/56939/2-500)
- [Set up UET tags using Shopify, WordPress.com, and other website platforms](https://help.ads.microsoft.com/#apex/3/en/56940/2-500)
  - [Set up UET tags using Shopify](https://help.ads.microsoft.com/#apex/3/en/56901/-1)
  - [Set up UET tags using WordPress.com](https://help.ads.microsoft.com/#apex/3/en/56902/-1)
  - [Set up UET tags using BigCommerce](https://help.ads.microsoft.com/#apex/3/en/56900/-1)
  - [Set up UET tags using Wix](https://help.ads.microsoft.com/#apex/3/en/56903/-1)
- More FAQ: [Universal Event Tracking](https://help.ads.microsoft.com/#apex/3/en/53056/2-500)