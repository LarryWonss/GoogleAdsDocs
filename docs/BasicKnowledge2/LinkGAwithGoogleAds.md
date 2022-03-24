# 1

> [!warning]
>
> 由于GA和Google Ads对于转化的跟踪逻辑其实是不同的，所以两边记录到的转化数据不一致是必然存在的，减少两边转化跟踪的统计差异，主要可以从以下几个方面入手：
>
> - 两边均采用Last Click作为归因；
> - 把GA统计到的通过广告带来的转化回传到Google Ads账户中
>
> 那么第二个措施，如何把GA统计到的从Google广告过去的转化回传到Google Ads广告账户中呢？

1. 在Google广告账户后台，`Tools & Settings >>> Conversions；`![image-20210720141123910](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720141123910.png)

2. 点击`➕`；![image-20210720141446237](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720141446237.png)

3. 选择`Import >>> Google Analytics (UA)`，并继续；![image-20210720141616065](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgphotosimage-20210720141616065.png)

4. 在弹出的窗口中，选择你需要导入和跟踪的转化数据；

    > [!note]
    >
    > - 电商类，非购买转化，推荐不用计入Conversions中，Conversions中只包含直接的购买转化；
    > - 所有转化计算次数，推荐在Cookie有效期内只算一次，**但针对购买转化，统计每一次转化**；

