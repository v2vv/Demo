![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

最后发布:2019-01-17 10:48:46首次发布:2019-01-17 10:48:46

    1.查看所有数据库
    show databases;
    2.使用数据库
    use 数据库名;
    3.查看当前使用的数据库
    select database();
    4.创建数据库
    create database 数据库名 charset=utf8;
    例：
    create database python charset=utf8;
    5.删除数据库
    drop database 数据库名;
    例：
    drop database python;
    

*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarThumbUp.png) 点赞 1 
*    [![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarComment.png) 评论](https://blog.csdn.net/weixin_43192242/article/details/86519739?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-2.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-2.channel_param#commentBox) 
*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect.png) 收藏 
*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarMobile.png)  手机看 
    
    分享到微信朋友圈
    
    x
    
    ![](data:image/png;base64,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)
    
    扫一扫，手机阅读
    
*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarReward.png) 打赏 
    
    打赏
    
     [![](https://profile.csdnimg.cn/5/F/A/3_weixin_43192242)](https://blog.csdn.net/weixin_43192242) 
    
    positivehua
    
    你的鼓励将是我创作的最大动力
    
    C币 余额
    
    ¥2 ¥4 ¥6 ¥10 ¥20 ¥50
    
    您的余额不足，请先充值哦～[去充值](https://i.csdn.net/#/wallet/balance/recharge)
    
*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/lookMore.png) 
    *   文章举报
*   关注
*   一键三连
    
    点赞Mark关注该博主, 随时了解TA的最新博文![](https://csdnimg.cn/release/blogv2/dist/pc/img/closePrompt.png)

12-21 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png) 33万+ 

04-02 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png) 131 

 ![](https://g.csdnimg.cn/static/user-img/anonymous-User-img.png) 

03-22 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png) 1669 

07-21 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png) 168 

03-13 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png) 819 

12-21 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png) 107 

02-27 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png) 2659 

05-14 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png) 251 

07-11 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png) 4573 

11-05 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png) 7355 

©️2020 CSDN 皮肤主题: 精致技术 设计师:CSDN官方博客 [返回首页](https://blog.csdn.net/)