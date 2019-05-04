# 第 7 周  20190422-0428

## Algorithm


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

