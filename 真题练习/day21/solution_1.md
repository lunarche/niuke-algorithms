### [彩色砖块](<https://www.nowcoder.com/practice/8c29f4d1bea84d6ba2847e079b7420f7?tpId=182&&tqId=34308&rp=1&ru=/ta/exam-all&qru=/ta/exam-all/question-ranking>)

小易有一些彩色的砖块。每种颜色由一个大写字母表示。各个颜色砖块看起来都完全一样。现在有一个给定的字符串s,s中每个字符代表小易的某个砖块的颜色。小易想把他所有的砖块排成一行。如果最多存在一对不同颜色的相邻砖块,那么这行砖块就很漂亮的。请你帮助小易计算有多少种方式将他所有砖块排成漂亮的一行。(如果两种方式所对应的砖块颜色序列是相同的,那么认为这两种方式是一样的。)
例如: s = "ABAB",那么小易有六种排列的结果:
"AABB","ABAB","ABBA","BAAB","BABA","BBAA"
其中只有"AABB"和"BBAA"满足最多只有一对不同颜色的相邻砖块。

```
输入描述:
输入包括一个字符串s,字符串s的长度length(1 ≤ length ≤ 50),s中的每一个字符都为一个大写字母(A到Z)。
输出描述:
输出一个整数,表示小易可以有多少种方式。
示例1
输入
ABAB
输出
2
```

##### 分析

还以为自己没理解他的意思：只要任意两种字符之间满足其相邻的个数小于等于1即可，是我想的太多

```python
char_set = set(list(input()))
print(0) if len(char_set) > 2 else print(len(char_set))
```

```c++
#include<bits/stdc++.h>
using namespace std;

int main()
{
    string s;
    cin >> s;
    set<char> char_set;
    for(auto c:s)
        char_set.insert(c);
    if (char_set.size() > 2)
        cout << 0 << endl;
    else
        cout << char_set.size() << endl;
    return 0;
}
```

- C++ set相关函数

``` 
insert(val)  //插入元素
find(val)   //查找，找到了就返回对应位置的迭代器，否则返回end()
```

