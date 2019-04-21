# 第 6 周  20190415-0421

## Algorithm


## Review

#### 1. [Removal of mapping types](https://www.elastic.co/guide/en/elasticsearch/reference/6.0/removal-of-types.html)

ES 6.0 之后只支持一个index对应一个type,5.0 创建的多应用也可以再6.0中使用，7.0弃用，8.0去掉；嵌套类型需要使用 [**join**](https://www.elastic.co/guide/en/elasticsearch/reference/6.0/parent-join.html) 字段

ES 使用 type 和 文档 id 生成一个 uid唯一标识，因此具有相同_id的不同类型的文档可以存在于一个索引中。

在一个Elasticsearch索引中，不同映射类型中具有相同名称的字段在内部由相同的Lucene字段支持。所以两个相同的字段必须具有相同的字段定义。

最重要的是，存储在同一索引中具有很少或没有共同字段的不同实体会导致数据稀疏，并影响Lucene有效压缩文档的能力。

每个文档类型使用一个 index,数据更稠密，全文索引也更准确

多类型迁移使用 [**Reindex API**](https://www.elastic.co/guide/en/elasticsearch/reference/6.0/docs-reindex.html)


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

