### [分玩具](<https://www.nowcoder.com/practice/a4771283f1c9435d9aeb3045d55dc030?tpId=170&&tqId=34076&rp=1&ru=/ta/exam-sohu&qru=/ta/exam-sohu/question-ranking>)

幼儿园里有有M个小朋友在课件玩耍，每个人手中现有ni个玩具。为了公平起见，老师需要让每个小朋友手中有相同数量的玩具。假设老师每次只能从一个人手中拿走两个玩具并给另一个小朋友。求老师最少需要做多少次这样的玩具转移。如果不存在可行的方案则输出-1。

```
输入描述:
每个输入包含一个测试用例。每个测试用例的第一行包含一个整数M（1 <= M<= 100），接下来的一行包含M个整数ni（1 <= ni <= 100）。
输出描述:
输出一行表示最少需要移动多少次可以平分苹果，如果方案不存在则输出-1。
示例1
输入
4
7 15 9 5
输出
3
示例2
输入
2
3 6
输出
-1
```

#### 分析

计算出均值，然后对每一个小于均值的计算需要的次数，如果不能整除2的话说明不存在方案。

```python
N = int(input())
nums = list(map(int,input().split()))

if sum(nums)%N !=0:
    print(-1)
else:
    mean_val = sum(nums)/N
    cnt = 0
    for val in nums:
        if val < mean_val:
            if (mean_val-val)%2==0:
                cnt += (mean_val-val)/2
            else:
                print(-1)
                break
    print(int(cnt))
```

