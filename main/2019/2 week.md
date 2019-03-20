20190318-0324

### Algorithm

[最长回文子串]([https://elanderson.net/2018/04/run-multiple-projects-in-visual-studio-code/](https://leetcode-cn.com/explore/interview/card/tencent/221/array-and-strings/896/))

>回文是一个正读和反读都相同的字符串，例如，“aba” 是回文，而 “abc” 不是。

#### 1.简单粗暴式解法
   
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


### Review


### Tip


### Share

