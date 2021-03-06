### [shopee的办公室](<https://www.nowcoder.com/practice/a71f3bd890734201986cd1e171807d30?tpId=179&&tqId=34270&rp=1&ru=/ta/exam-other&qru=/ta/exam-other/question-ranking>)

shopee的办公室非常大，小虾同学的位置坐落在右上角，而大门却在左下角，可以把所有位置抽象为一个网格（门口的坐标为0，0），小虾同学很聪明，每次只向上，或者向右走，因为这样最容易接近目的地，但是小虾同学不想让自己的boss们看到自己经常在他们面前出没，或者迟到被发现。他决定研究一下如果他不通过boss们的位置，他可以有多少种走法？

```
输入描述:
第一行 x,y,n (0<x<=30, 0<y<=30, 0<=n<= 20) 表示x,y小虾的座位坐标,n 表示boss的数量（ n <= 20）
接下来有n行, 表示boss们的坐标(0<xi<= x, 0<yi<=y，不会和小虾位置重合)
x1, y1
x2, y2
……
xn, yn
输出描述:
输出小虾有多少种走法
示例1
输入
3 3 2
1 1
2 2
输出
4
```

#### 分析

- 问题中的位置和方向描述的很迷惑
- 构造`x*y`的dp数组，`(0,0)`为起始位置，到`(x,y)`的路径数
- 转移方程：`dp[i][j] = dp[i-1][j]+dp[i][j-1]`
- `basecase`:对每一个非boss的点其路径均为1，boss处为0，dp计算中遇到boss点跳过。

```python
x,y,n = list(map(int,input().split()))
dp = [[1]*(y+1) for _ in range(x+1)]

for _ in range(n):
    boss_x,boss_y = list(map(int,input().split()))
    dp[boss_x][boss_y] = 0
for i in range(1,x+1):
    for j in range(1,y+1):
        if dp[i][j] != 0:
            dp[i][j] = dp[i-1][j]+dp[i][j-1]
            
print(dp[-1][-1])
```

