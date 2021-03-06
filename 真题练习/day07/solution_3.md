### [N-GCD](<https://www.nowcoder.com/practice/97142035f7d2443c91a3ffc343ad691d?tpId=122&&tqId=33724&rp=1&ru=/ta/exam-wangyi&qru=/ta/exam-wangyi/question-ranking>)

小明很喜欢数对，又很喜欢GCD(最大公约数)。所以他想尽办法创造了一种全新的最大公约数：
给出若干个数对(ai,bi)，如果一个最大的质数x可以整除每一个数对中的至少一个数字并且这个数字大于1，那么x就称为这些数对的N-GCD。
现在小明给了你一些数对，希望你可以算出它们的N-GCD。

```
输入描述:
第一行一个数字n，表示数对的个数。
接下来n行，每行两个数字，用一个空格分隔，表示一个数对。
满足1<=n <=150000,1<=ai,bi<=2 * 10^9。

输出描述:
一个数字，这些数对的N-GCD；若N-GCD不存在，那么输出-1。
示例1
输入
复制
3
2 2
3 6
7 8
输出
复制
2
示例2
输入
复制
2
18 12
3 24
输出
复制
3
```

#### 分析

在读取数字的时候顺便计算下最小值min，之后找出`[2,min]`之间的素数，并从大到小遍历，判断该数能否整除除`nums`数组中每一个数对中的任意一个值。

```python
from math import sqrt

def is_prime(a):
    for i in range(2,int(sqrt(a)+1)):
        if a%i==0:
            return False
    return True
    
N = int(input())
nums = []
min_val = 1e9
for i in range(N):
    val1,val2 = list(map(int,input().split()))
    min_val = min(min_val,val1,val2)
    nums.append([val1,val2])

primes = []
res = 1e9
for i in range(min_val,1,-1):
    if is_prime(i):
        primes.append(i)
        
for val in primes:
    satisfied = True
    for i in range(N):
        if nums[i][0]%val!=0 and nums[i][1]%val!=0:
            satisfied = False
            break
    if satisfied:
        res = val
        break
        
print(res) if res!=1e9 else print(-1)
```

