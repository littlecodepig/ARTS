# 第二周 20190318-0324

## Algorithm

[最长回文子串]([https://elanderson.net/2018/04/run-multiple-projects-in-visual-studio-code/](https://leetcode-cn.com/explore/interview/card/tencent/221/array-and-strings/896/))

>回文是一个正读和反读都相同的字符串，例如，“aba” 是回文，而 “abc” 不是。

#### 1.简单粗暴式解法

leetcode会提示时间超过限制

分析：

    1. 遍历求出字符串中所有的子串，即0-1，0-2，0-3 ... 0-n ... n-1-n；
    2. 遍历这些子串获取到所有回文串；
    3. 取这些回文串中长度最大的；
    4. 边界情况，字符串为空；字符串只有一个字符；

代码实现：

        public static string GetLongestCommonSubString(string s)
        {
            var len = s.Length;
            if(len ==0) return string.Empty;
            var array = s.ToArray();
            var start=0;
            var maxLength=0;

            for(int i =0;i<len;i++)
            {
                for(int j=i+1;j<len;j++)
                {
                    //遍历子串是否是回文                    
                    for(int tmpi=i,tmpj=j;tmpi<tmpj;tmpi++,tmpj--){
                        if(!array[tmpi].Equals(array[tmpj]))
                        {
                            break;
                        }
                        if(tmpi+1 >= tmpj-1 && j-i >= maxLength)
                        {
                            start =i;
                            maxLength =j-i+1;
                        }
                    }
                }
            }
            return s.Substring(start,maxLength ==0?1:maxLength);
        }  

#### 2.动态规划




## Review


## Tip

#### 1. 动态规划 DP (dynamic programming)

将一个问题拆成几个子问题，分别求解这些子问题，即可推断出大问题的解。寻找最优子结构，即从小规律，推导出 f(n)。
[什么是动态规划？动态规划的意义是什么](https://www.zhihu.com/question/23995189)

#### 2. web.config配置获取顺序

1. 机器:machine.config:位于 FRAMEWORK\CONFIG(FRAMEWORK一般是c:\winnt\Microsoft.NET\Framework\version)，是.net必须备的默认配置文件；
2. 站点:web站点根目录下的web.config，影响全站配置；
3. 程序:应用程序虚目录根下的web.config，影响全虚目录配置；
4. 子目录:虚目录的子目录下的web.config，影响该子目录及其子目录下配置；
   
**web.config用来修改.net默认配置。**

Blog链接：[ASP.net(1.1)原理学习笔记--第三章 配置Configuration](http://www.cnblogs.com/deepcast/archive/2005/08/08/210348.html)

## Share

嗯，第二周了 ，主要分享一下，本周的一些工作复盘，一些心得，以及正在看的书的一些体会把。

1.工作复盘

本周主要主要的工作是是开发一个功能模块，并统筹整个功能模块的开发进度。小团队一共3个人，工作量适中。**问题1：**开发初期，听了整个需求，并排了整个功能计划，并分别指派给了我以及其它两人，但开发过程中，随着开发的不断深入，针对一些零碎的需求，具体的开发人员可能需要针对每一个细节的case进行编码，这时候就扣出来很多细枝末节，虽然我对整个功能要求很清楚，但当具体到某一个功能细节之处时还是发现**不明确**，然后再去询问产品经理，明确细节，虽然里面有一部分产品也没考虑到，但我想是不是再讨论需求时可以提前意识的这些小case，并提前指出并加以讨论，还是是不是再梳理功能清单的时候，尽量考虑到每个功能点以及比较较重要的case呢？尽量明确出来所有可能导致疑问的地方，让开发人员可以比较专注的完成功能。**问题2：**目前工作量的分配问题，目前功能的工作量的分配，都是按比较宽松的方式分配的，但是有些开发人员还是会表示各种问题之类的，不知道是不是个人主观判断存在误差导致，这方便还需要进一步锻炼吧。**问题三:** 人员管理问题，虽然只有两个人但是，发现有的人积极性非常差，而且对自己的要求非常低，和其它人沟通后，需要明确具体的功能以及相应的截止时间。

2.一些心得

分配功能任务时，还需要尽可能的细一下，考虑的更详细一些，有些问题提前想到，开发过程中可能就回想走很多的弯路；可能每个人都有自己的工作态度，也不必强求，共同保证任务按时完成即可，平常心一点；终于知道体会到什么叫烂代码的味道了，就是，那还总一个函数写了好几屏，各种if逻辑，各种临时变量，让你看的头昏脑胀，中间搀杂着各种重复代码，看的非常痛苦 :-(

3.《重构》

本周重构看到第226页，Replace Type Code with SubClasses(以子类取代类型码)，利于多态将我们代码中的 switch 或 if...else.. 等分支挪移到子类中去，从而使我们的代码更简洁，更加清晰易于理解。现在越看《重构》这本书，越觉的，有点想设计模式的指导实现步骤说明，感觉结合设计模式一起看可能效果倍增


