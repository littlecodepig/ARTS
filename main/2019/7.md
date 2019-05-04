# 第 7 周  20190422-0428

## Algorithm
[回文数](https://leetcode-cn.com/problems/palindrome-number/)

        public static bool IsPalindrome(int x) 
        {            
            if(x<0 || x>int.MaxValue)
            {
                return false;
            }
            var array = x.ToString().ToArray();
            var str =string.Empty;
            for(int i=0;i<array.Length;i++)
            {
                str =str+array[array.Length-1-i];
            }              
            if(x == Convert.ToInt64(str))
            {
                return true;
            }
            return false;            
        }


## Review

发现一直以来使用单元测试的方式都是错误的，单元测试应该只关注单元测试的方法的，输入输出，不需要连DB不需要访问其他以来的资源，使用mock即可。

文件介绍了使用fakes框架进行mock的方式
1. stub : 本代码库的，面向接口编程的；
2. shim ：隔离依赖的第三方库

![](https://docs.microsoft.com/zh-cn/visualstudio/test/media/fakes-2.png?view=vs-2015)

## Tip

#### Introduce Null Object 引用null对象

针对大多数客户端代码需要对空对象做出相同的响应的时候，我们可以使用此重构手法，用一个空对象实现统一的响应内容，从而简化客户端代码，使便面内聚到空对象中，统一控制。

如何使用，１）使用多态，创建一个nullxxx类继承自源类，添加isnull函数，返回true,并实现相应的空响应方法；2）对于不能修改源类的情况下，可以使用创建一个空接口，并创建一个nullxxx类继承源类，并实现这个接口，可以通过判断是否实现了这个接口类型从而知道这个实例是是否是个nullobject。

## Share

月底功能顺利上线，算是相当完美吧:-) 

本周复盘，就是发现人真的是最难管理的，和一些同事合作一段时间也慢慢发现了各种问题，感觉一度想撂挑子，不过想到，爬山虽然困难，达到的高度也会大不一样，咬牙继续坚持把，困难终将使我们变的强大。对于积极性查的人，需要明确细分任务，并做好deadline，明确出来。对应想做写东西的人来说要多放一些发挥的空间出来。

一些不足吧，对于一些琐碎的事情，发现番茄工作法有点不太适用了，看来需要摸索一个针对琐碎事情的工作方法；有时候可能需要控制下自己的心态，不能崩，针对别人做的不好的地方还是需要委婉点，发现自己有点太直接了，可能对别人有一定的伤害，最大的不足还是需要更合理的做好时间规划，提供效率。