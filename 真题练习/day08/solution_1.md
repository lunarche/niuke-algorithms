### [美妙的约会](<https://www.nowcoder.com/practice/cc3eef5aed91489f9b706f4196e0d5c6?tpId=122&&tqId=33726&rp=1&ru=/ta/exam-wangyi&qru=/ta/exam-wangyi/question-ranking>)
题目描述
牛牛和妞妞在一天晚上决定一起去看一场情人节演唱会，可是由于这场演唱会实在太出名了，有很多情侣都来观看，牛牛和妞妞不小心被人流冲散了！
维持秩序的人决定，让大家排成一列，相邻两个进去的人（2k-1和2k，k为正整数）坐在相邻座位。但是现在的队伍乱糟糟的，有很多情侣都不在相邻位置。维持秩序的人同意让情侣们跟相邻的人交换位置，直到所有情侣都在2k-1和2k位置上为止。
但是维持秩序的人很没有耐心，所以需要最少的交换次数，你能帮情侣们算出这个次数吗？

```
输入描述:
第一行一个整数n，表示一共有n对情侣，编号从1到n。同一对情侣编号相同。1<=n<=100
第二行2n个整数ai，表示编号为ai的情侣在第i个位置。1<=ai<=n
输出描述:
一个整数，代表最少交换次数。
示例1
输入
3
3 3 2 2 1 1
输出
0
示例2
输入
4
1 2 3 4 1 2 3 4
输出
6
```

- 暴力法，挨个找相同的值，之后模拟交换过程把这两个值弹出，重复计算剩下的情侣们。

```python
N = int(input())
nums = list(map(int,input().split()))

times = 0
while len(nums) > 1:
    temp = nums.pop()
    if temp == nums[-1]:
        nums.pop()
        continue
    for i in range(len(nums)-1,-1,-1):
        if temp == nums[i]:
            times += (len(nums)-i-1)
            nums.pop(i)
            break
print(times)
```

