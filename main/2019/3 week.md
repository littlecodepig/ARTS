# 第3周  20190325-0331

## Algorithm


## Review

https://simpleprogrammer.com/store/products/learn-anything-quickly/

首先这个网站挺不错，是通过看 原则 那本书知道的, 这文章说了，我们应该学会如何高效的学习，而不是追逐各种各样的技术，或者一个技术的全部细节，因为你现在知道的知识，五年后可能超过50%会过时。而且即使你通读了整个教程，真正开始做的时候，可以记住的也是少数，成功的开发者这都是深入某项技术，掌握其中的20%重要的部分，并以此可能进行工作即可，细节可以带着问题再去学习，可以事半功倍。

> So I expected that the tradeoff for rapid learning is a shallower understanding and less ability to apply what you’ve learned.
> **作者的观点：** 所以我认为快速学习的代价是肤浅的理解和应用所学知识的能力。

## Tip

#### 1. 以 State/Strategy 取代类型码 (Replace Type Code with State/Strategy)

该重构方法主要是处理一个复杂的多个条件表达式，多个switch的情况，我们可以使用此方法将多个 case 分别迁移到不同的类中，使得职责单一。具体做法就是，1）定义一个抽象类型；2）让不同 case 的类型继承抽象父类；3）调整源文件中使用的方法，改成抽象类型进行调用。

此方法去掉了 type code 逻辑却生成了一个生产类型子类的 switch ，但不用担心，这不是无用的，而是可以采用工厂方法进一步重构，当然这是后续的重构方法。文中也给出来具体的页码。这也是这本书的两点啊，可以很方便的找到相关联的重构方法。

#### 2. Replace Subclass with Fields (以字段取代子类)

该方法主要是删减调过度设计的继承关系，将简单的继承关系合并到父类中，并干掉子类，主要做法：1）将所有子类的引用都转换成对父类的引用；2）将子类的的属性和方法挪移到父类中；

#### 3. IE8下，使用 date()兼容问题
使用 new date('yyyy-MM-dd') 形式进行初始化，再chrome下正常，再IE8 下面显示 NaN ,初始话日期问题，使用 yyyy/MM//dd 日期格式问题解决。

#### 4. 英语单词

full stack developer 全栈开发

## Share

