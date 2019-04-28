# 第 6 周  20190415-0421

## Algorithm


## Review
https://docs.microsoft.com/zh-cn/visualstudio/test/isolating-code-under-test-with-microsoft-fakes?view=vs-2015

发现一直以来使用单元测试的方式都是错误的，单元测试应该只关注单元测试的方法的，输入输出，不需要连DB不需要访问其他以来的资源，使用mock即可。

文件介绍了使用fakes框架进行mock的方式
1. stub : 本代码库的，面向接口编程的；
2. shim ：隔离依赖的第三方库

![](https://docs.microsoft.com/zh-cn/visualstudio/test/media/fakes-2.png?view=vs-2015)

## Tip

#### 1. 使用 ajaxFileUpload.js 上传文件，文件上传成功，获取不到值

问题原因：主要是因为 ajaxFileUpload.js 组件会动态生成一个 iframe 进行 formdata 表达提交请求数据到后端，后端返回数据到这个iframe时，浏览器判断到跨域问题了，由于安全问题（？）自动就出错了。

解决措施：直接再动态创建 iframe 的地方直接指定域名： **document.Domain = 'xxx.com'** 配置主域名即可；

参考：

1. https://blog.csdn.net/u012927379/article/details/51259430
2. https://blog.csdn.net/joyhen/article/details/21631833
3. http://www.thanks.live/index.php/posts/request_cross_domain
4. 

## Share

