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

https://learning.getpostman.com/docs/postman/environments_and_globals/variables/

主要介绍了 PostMan 中变量的说明：[Variables](https://learning.getpostman.com/docs/postman/environments_and_globals/variables/),
按照作用域，变量可以分为以下5类：

1. Global
2. Collection
3. Enviroment
4. Data
5. Local

![官方图片](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/scopes.png)


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

第四周，本周加班比较多，继续做一些复盘吧。

1.工作复盘

1）本周功能测试并上线，测试阶段还是发现存在很多没有想到的问题，比如：浏览器兼容性问题，UI问题。过测试用例的时候，还是要尽量明确所有case，功能不仅仅是UI上的哪些流程，很多后台的实现可能关联好几方人员，产品可能并不关心具体的实现细节，所以和测试介绍相关功能的时候，点可能没有那么细，这时候应该及时提出来，明确所有细节避免不必要的纠纷；2）就是目前发现发现，测试阶段还是会出现一些小细节可能产品并没有考虑的，导致了一些小case的调整，但这些还是必须要调整，所以开发人员开发的时候还是要尽量将发现的问题，以及一些不合理的细节提出来，尽量避免后期阶段程序调整把。3）重构了一些功能逻辑，测试阶段发现有些逻辑被重构没了，重构的时候还是需要尽量细心，做好单元测试；4）本周有一些临时需求，需要紧急上线所以连这两天都有上线，事后想了下，需求虽然急但是，完全应该可以提前上线的，但是每次改动都要拖到快下班了才能测试，仿真环境测一遍，线上模拟走一遍，线上再来一遍，中间在出现点其它问题，一晚上就下去了，问题到底应该算谁的呢？

2.一些思考

发现对于哪些最起码工作态度都存在问题的，既然无法改变他们，就应该远离他们简直就是来制造混乱的，对事不对人，无法改变别人，只能让自己和这种人隔绝起来，不过想想，还是尽量保持一个平和的心态把。
