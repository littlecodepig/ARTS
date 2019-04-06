# 第4周    20190401-0407

## Algorithm

[无重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/solution/)

代码：

        private static int LengthOfSubString(string s)
        {
            var len = s.Length;
            var list = s.ToArray();
            var maxSubLen = 0;

            HashSet<char> set = new HashSet<char>();
            int i=0,j=0;
            while(i<len && j < len)
            {
                if(!set.Contains(list[j]))
                {
                    set.Add(list[j++]);
                    maxSubLen = Math.Max(maxSubLen,j-i);
                }
                else{
                    set.Remove(list[i++]);
                }

            }
            return maxSubLen;
        }

[Z 字形变换](https://leetcode-cn.com/problems/zigzag-conversion/)

代码：

        private static string ConvertZ(string s,int numRows)
        {            
            if(string.IsNullOrEmpty(s) ||s.Length <= numRows || numRows ==1){
                return s;
            }
            var len = s.Length;
            var columns = len/numRows;
            var array = s.ToArray();
            var result = string.Empty;
            Func<int,int> func = (t)=>{return t*(2*numRows-2);};
            //每行间距都是，2n-2
            int i=0,j=0;
            while(i < numRows){
                if(j<=columns){
                    //第一列
                    if(j==0){
                        result+=array[i];
                    }else {
                        //非第一和最后一行
                        if(i!=0 && i!=numRows-1&& func(j)-i<len) 
                            result+=array[func(j)-i];
                        if( func(j)+i<len ){
                            result+=array[func(j)+i];
                        }     
                    }                                   
                    j++;
                }
                else{
                    j=0;
                    i++;
                }
            }
            return result;
        }


## Review


## Tip

#### 1.Decompose Conditional（分解条件表达式）

将复杂的条件表达式分解到独立的函数中，一方面使原来的条件语句更加简单清晰，以方便可读性更强。

#### 2.Consolidate Conditional Expression(合并条件表达式)

将包含相同返回的多个条件表达式，移动到一个函数中，从而简化复杂的一堆判断逻辑

#### 3.Consolidate Duplicate Conditional Fragments(合并重复的条件片段)

没什么可说的，拒绝重复代码，将不同条件分支中的相同逻辑提取到条件判断外面。

#### 4.Remove Control Flag(移除控制标记)

使用break/continue/return,移除多余的控制flag 临时变量，从而言之就是要让代码更简洁。

## Share

