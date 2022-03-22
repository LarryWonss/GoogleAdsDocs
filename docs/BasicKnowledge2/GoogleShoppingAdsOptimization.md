# 购物广告系列的优化策略

> 购物广告其实略简单。简单来理解，购物广告就是一种特殊的产品图文展示型的搜索广告「潜在客户搜索关键词（SearchTerms）触发我们的产品或网站展示」；我们「广告主」将我们网站所有商品信息以Feed文件的形式提交到Google Merchant Center，实际我们投放购物广告时，谷歌从Feed中提交的产品，千人千面展示给高购买意向的潜在客户。那这种类型的广告在实际的投放过程中，如何进行优化呢？下面，结合我自己的实践经验，做简单总结：

****

##### No.1 投放前：做好账户架构和命名规范

![image-20210818101417614](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210818101417614.png)

就如上图所示，这里广告账户的架构非常简单，只投放了一个类目，那就是网站上的Best Seller这个分类的产品。因为我账户是多国家投放，所以这里在系列名中区分了各个国家：

```
- Google_PL_US_Best_Seller_tROAS_0518
- Google_PL_AU_Best_Seller_tROAS_0715
- Google_PL_CA_Best_Seller_tROAS_0715
- Google_PL_NZ_Best_Seller_tROAS_0715
- Google_PL_UK_Best_Seller_tROAS_0813
```

我系列的命名规则是：**渠道名_ 广告类型 _国家 _投放类目 _ 出价方式 _日期**

- 投放的是谷歌广告，为啥还要多此一举标识Google这个渠道名呢：
  - 因为通常来说，客户通常不会是只投放谷歌一个渠道，如果各个渠道都采用我这套命名规则，容易系列名重复，标识好渠道名，方便广告主在Google Analytics后台追踪和分析各个广告渠道的整体效果；
- 广告类型简写：
  - `PLA`： Product Listing Ads = Shopping Ads，PLA广告就是Prodcut Listing Ads的简写，是Google早起对购物广告的称呼，现大家称ShoppingAds比较多，命名不建议用SA简写，因为Search Ads简写也是SA；
  - `SA`：Search Ads搜索广告的简写
  - `DA`：Display Ads展示网络广告的简写



回归到账户架构，如果我们的账户投放的是多个国家的多类目的，那么我们的账户可以按照以下结构进行设置：

**Google_ [ PL/SA/DA ] _ [ US/CA/AU/UK/NZ]_ [Best_Seller/Coat/Hat/Shoes/Dress/NewArrival] _ [tROAS / eCPC/ tCPA /etc] _Date**

****

##### No.2 投放时：按类目投放/测试

如上面命名规范中提到的，如果我们账户中需要投放多个类目，我们首先应该在Campaign系列命名中进行区分，同时在选择产品进行投放的时候，选择对应的Catagory或者按照Custom_Label进行分类；![image-20210818110957846](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210818110957846.png)![image-20210818111053975](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210818111053975.png)![image-20210818111150438](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210818111150438.png)

**1、Question：为啥要按照这个类目来投放呢？**

- 如果你投放全站所有产品，那么广告见效一定非常慢，浪费的广告预算一定不少；分类目投放，是测试出利基款产品/类目产品/新品，最快的方式；通常来说，投放网站自然流量转化效果都不错的产品，付费广告的效果通常来说都不会差；利用谷歌购物广告快速测品，单独筛选出需要测试的产品「这些产品肯定有共同点」，针对性投放测试是最快速的测试方式，比如你要测试网站拥有某个共同花色/元素/款式的产品是不是可以长期投放；

**2、Question：怎么通过Custom Label 筛选出高客单价产品、热卖款产品、新款产品？**

- 这是一个有意思的问题，你需要非常了解Feed文件中各个字段的实际含义，**[点击前往](https://support.google.com/merchants/answer/7052112?hl=zh-Hans&ref_topic=6324338)** 了解，着重了解一下 **[自定义标签](https://support.google.com/merchants/answer/6324473?hl=zh-Hans&ref_topic=6324338)** ，如果SKU不多的话，你可以在Feed文件中的Custom Label标签中手动分别把热卖款、新品、利基款产品、高客单价等产品填写好对应的标签；这样你在实际操作购物广告选择需要投放的产品时，你就可以按照Custom Label进行投放了；这里额外提一下我目前使用用户体验非常好的建站平台**[Shopyy](https://accounts.shopyy.com/h-user-register.html?invite=lds)** 配合其插件 **「Google Shopping同步工具」**，从技术层面解决了这些难题，再也不用手动一个个打标签了！![image-20210818115026927](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210818115026927.png)



****

##### No.3 数据稳定期：过滤杂质流量，提高搜索词精准度

> 在投放了一段时间后，我们就需要针对各个广告系列进行数据分析了，判断一下哪些类目、哪些国家、哪些具体产品数据表现较好，哪些产品、哪些类目、哪些国家需要优化，以及哪些需要被优化掉！具体怎么执行这些优化操作呢？这里我用我账户的实际数据来示例。



###### 1. 先从产品层面入手，优化掉花费多但不出单的产品，加入表现优异的产品

**具体操作：**在对应的Custom Label中删除这些花费较多但不出单或出单成本高于该系列平均水平且ROAS表现不佳的产品的自定义标签，同时加入其它表现较好但不在这个商品列表中的产品。如下图中ID为**csg7500**的产品，花费78.5美金，但是0️⃣转化，这个已经远低于我整个购物系列的平均水平了，那么这个时候，我就会在Feed文件中删除这个产品的Best Seller标签；同时我会在GMC中继续观测，看哪些产品的转化好且ROAS优于整个账户的购物广告系列，在这些产品的自定义标签上添加上Best Seller标签，以便我接下来的这条针对网站热卖款产品的广告系列的效果会越来越好。![image-20210818120422595](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210818120422595.png)

****

###### 2. 分析Search Terms数据，排除掉一些杂志流量

> 分析Search Terms的目的很简单：查看触发购物广告的实际用户搜索的词有哪些，哪些花费较多但转化差，哪些点击率差，哪些转化率差。

![image-20210818122004155](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210818122004155.png)

比如上面我框选的这几个**Search Terms**，我是**按照Cost来降序排列**的，这些词算花费靠前，但是没有转化，在你的**容许测试预算（每个客户都未必相同，只推荐跟账户平均水平比较）**范围内，如果你觉得这些词花费较多，且效果较差，就可以把这些词加入到Negative Keywords「否定关键词」列表中，那么下一次当有用户搜索这些字词的时候，我们的广告就不会再展示出去了，这样我们的广告预算就可以更加有效，浪费的预算就会减少。

****

###### 3.针对不同设备，差异化出价

> 在4G网络还没有大力普及的时候，用户基本会在PC端成交，随着4G网络的大力发展，甚至当下的5G网络快速迅猛发展，移动端的成交比例越来越多，所以，当下针对移动端、传统PC桌面端和平板设备端进行差异化出价就非常有必要了。

![image-20210818122733647](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210818122733647.png)

如上图所示，各个设备端的数据表现各有差异，可以从各个流量端的消耗占比、ROAS数据、CPC数据等决定如何差异化订单，像我这里，就针对PC端进行了20%的降低出价，针对平板端进行了30%的降低出价，因为我使用的是tROAS竞价策略，实际跑出来的CPC数据未必PC端就比移动端低，但相对于大盘水平来说，PC端肯定会比大盘平均CPC低。

****

###### 4. 查看Segment数据，定期关注广告变化趋势

> Segment可以按照时间、点击类型、转化以及广告展示出去的Network查看分维度的数据。

如果你在Campaign层级设置中勾选了展示网络广告，可以查看Network维度数据，进行查看各个Website Publisher的效果，根据实际的广告效果排除一些效果表现不佳的Publisher，这个在 **Bing渠道** （**[点击联系Bing开户经理](https://www.brands.university/wp-content/uploads/2021/07/1626938508-1453624fafe0733.jpeg)**）可能表现更加明显。<img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210818125521249.png" alt="image-20210818125521249" style="zoom:50%;" />

<img src="https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210818125220753.png" alt="image-20210818125220753"  />



##### 小结：

Google购物广告优化，主要有以上4点可以进行优化，其中前两点又是最重要的优化方向。当然，类似的**Bing渠道**  的购物广告系列优化逻辑和方法，也可以参考这几个优化方向，大同小异。

