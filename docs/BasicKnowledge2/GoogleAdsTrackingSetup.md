# 



> 为了量化我们的广告投放成效，在Google广告账户后台直接统计到广告带来的转化成效，我们需要设置Google广告的转化代码，设置步骤如下：

1. 获取Google Ads 跟踪代码：
    - 获取入口：`Tools & Settings`>>>`Conversions`
        ![image-20220328155208105](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220328155208105.png)
        
    - 点击`New conversion action`
        ![image-20220328155451637](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220328155451637.png)
        
    - 电商网站：选择`Website`，进入到下一步；

    - Purchase事件跟踪设置如下：
        - Goal and action optimization：purchase
        - Conversion Name：purchase（***推荐保持和goal一致***）
        - Value：Use different values for each conversion
        - Count：Every
        - 其他设置：保持默认。
        
    - `Creat & Continue`，进入到代码部署界面。
        ![image-20220330150716975](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220330150716975.png)

2. 安装代码

    这里面有三种安装代码的方式：     

    > [!note]
    >
    > 三种方式安装转化跟踪代码，本质无差别，均是实现了同个目的。**将全局基础代码安装在网站的所有页面，将转化跟踪代码安装在订单提交成功页面(conversion page)**。

    - **自行手动安装：**适合有一定基础，懂代码的小伙伴;
        ![image-20220330151323291](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220330151323291.png)

    - **将代码发送给你们网站技术人员：**让其帮忙安装，如果自建站为纯自己搭建的，需要采用这种方式;
        ![image-20220330151241077](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220330151241077.png)

    - **借助Google代码管理工具GTM：**非常简单方便的一种方式，前提网站有安装好GTM代码管理容器。[![](https://img.shields.io/badge/去了解-GTM-brightgreen)](https://tagmanager.google.com/#/home)
        ![image-20220330151209443](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220330151209443.png)


    ​        

3. 安装示例：

    - 手动安装方式（以shopyy系统为例）

        1. 从手动安装步骤指示中获取两个关键代码信息：

            - AW-XXXXXXX：
            - AW-XXXXXXX/cyrX23jnhne9o

            ![image-20220330152315405](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimgimage-20220330152315405.png)

        2. 将以上两个信息复制黏贴到Shopyy后台；

            - 入口为：`配置>>>基础配置>>>广告追踪`；

            ![image-20220330152628684](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220330152628684.png)

            

            

    - 用GTM安装方式：

        1. 从安装引导页面获取Conversion ID和Conversion Label；
            ![image-20220330152831446](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220330152831446.png)

        2. 在GTM后台选择模块安装：

            - 点击`add a new tag`；

                ![image-20220330153146217](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220330153146217.png)

            - 选择代码类型并粘贴上面获取的Conversion ID和Conversion Label信息；
                ![image-20220330153248040](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220330153248040.png)
                ![image-20220330153424390](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220330153424390.png)

            - 在触发条件板块（triggering），选择all pages进行全局安装。
                ![image-20220330153652412](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220330153652412.png)

                > [!note]
                > 这里非常简单粗暴的选择了网站全部页面安装转化跟踪代码，如果你懂代码基础的话，可以进行更加细致的设置。思考路径：先在trigger板块定义出conversion page，然后将这里的触发逻辑限定在conversion page才触发。

                ![image-20220330154136814](https://iswott.oss-cn-shenzhen.aliyuncs.com/blog/imgimage-20220330154136814.png)

            - 最后保存提交变更即可。







