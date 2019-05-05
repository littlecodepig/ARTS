# 第 7 周  20190422-0428

## Algorithm


## Review

#### https://docs.microsoft.com/zh-cn/visualstudio/test/isolating-code-under-test-with-microsoft-fakes?view=vs-2015

发现一直以来使用单元测试的方式都是错误的，单元测试应该只关注单元测试的方法的，输入输出，不需要连DB不需要访问其他以来的资源，使用mock即可。

文件介绍了使用fakes框架进行mock的方式
1. stub : 本代码库的，面向接口编程的；
2. shim ：隔离依赖的第三方库

![](https://docs.microsoft.com/zh-cn/visualstudio/test/media/fakes-2.png?view=vs-2015)

## Tip

PathTooLongException with _GenerateBindingRedirectsIntermediateAppConfig

**解决方案：**

https://stackoverflow.com/questions/36641775/the-generatebindingredirects-task-failed-unexpectedly-the-specified-path-fil
https://github.com/Microsoft/msbuild/issues/1786

## Share

