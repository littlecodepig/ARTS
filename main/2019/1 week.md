20190311-0317

### Algorithm

>寻找两个有序数组的中位数, 给定两个大小为 m 和 n 的有序数组 nums1 和 nums2。
请找出这两个有序数组的中位数，并且要求算法的时间复杂度为 O(log(m + n))。
可以假设 nums1 和 nums2 不会同时为空。

分析：
 
1. m+n 是奇数，中位数再连个数组中；偶数，中位数再两个中间数的平均数；
2. m=0 或 n=0 ,只取一个数组的中位数即可；
3. 二分查找获取两个数组中的数据比较,k = (m+n)/2；

代码实现：

        private static double GetMiddleNumber(int[] a,int[] b)
        {
            var len = a.Length +b.Length;
            if(len % 2 ==0)
            {
                return (GetNumber(a,0,b,0,len/2)+GetNumber(a,0,b,0,len/2+1)) /2.0;
            }
            return GetNumber(a,0,b,0,(len+1)/2);
        }

        private static int GetNumber(int[] a ,int m ,int[] b , int n ,int k)
        {
            if(m >= a.Length)
                return b[n+k-1];
            if(n >= b.Length)
                return a[m+k -1];
            if(k==1)
                return Math.Min(a[m],b[n]);

            var p1 = m + k/2 - 1;
            var p2 = n + k/2 -1;
            var mid1 = p1 < a.Length ? a[p1]:int.MaxValue;
            var mid2 = p2 < b.Length? b[p2]:int.MaxValue;            

            if(mid1<mid2)
            {
                return GetNumber(a,m+k/2,b,n,k-k/2);
            }

            return GetNumber(a,m,b,n+k/2,k-k/2);
        }



### Review

本周分享一篇老外写的如何再 vscode 中同时 Debug 多个项目，非常适合同事调试多个微服务，链接如下：
[Run Multiple Projects in Visual Studio Code](https://elanderson.net/2018/04/run-multiple-projects-in-visual-studio-code/)

### Tip

分享 C# Tuple 的用法，不过返回值过多还是不建议使用，不然多个 Item 真的有点让你很抓狂。

1. 异类数据对象的有序集合，返回多个值可以使用，class/struct 的轻量级替代；
2. 最大支持8个参数，可以嵌套 tuple 进行扩展；
3. 第8个必须是tuple类型；

扩展：
C#6.0之前多返回值实现

1. KeyValuePair
2. ref / out
3. class / struct /dynamic
4. Tuple

C# 7.0 新增 Tuple 语法糖

    //方法返回值直接可以写多个返回值
    public (int param1,stirng param2) methodName(){

    }

### Share

第一周，刚加入学习小组，其实去年有看到耗子叔的专栏，并没有买，因为去年买了不少书和专栏，怕消化不了，前几天看到有活动，就买了，专栏先从最早的看了十几篇了，感觉很多内容说的很有道理，时间总是会有的，本来想计划就从下周开始把，看了耗子叔有篇文章说，你打游戏有时间，刷剧有时间，为什么就学习没有时间了呢，因为学习是“逆人性”的，确实自己老有想偷懒的想法，学习从来都是不轻松的，成功不是轻轻松松就能收获的，所以期待加入ARTS，希望收获更好的自己。
