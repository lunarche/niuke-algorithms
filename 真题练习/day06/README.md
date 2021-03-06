## day 06

### 1. [骰子期望](<https://www.nowcoder.com/questionTerminal/86ef0d5042934ef7819035794377a507>)
来源：[拼多多2020校招部分编程题合集](<https://www.nowcoder.com/test/23354036/summary>)

扔n个骰子，第i个骰子有可能投掷出Xi种等概率的不同的结果，数字从1到Xi。所有骰子的结果的最大值将作为最终结果。求最终结果的期望。

```
输入描述:
第一行一个整数n，表示有n个骰子。（1 <= n <= 50）
第二行n个整数，表示每个骰子的结果数Xi。(2 <= Xi <= 50)

输出描述:
输出最终结果的期望，保留两位小数。
示例1
输入
2
2 2
输出
1.75
```

#### [题解链接](./solution_1.md)

### 2. [二维表第k大数](<https://www.nowcoder.com/questionTerminal/98929bfe8f6b4beba5838285ae99aa6f>)

来源：[拼多多2020校招部分编程题合集](<https://www.nowcoder.com/test/23354036/summary>)

在一块长为n，宽为m的场地上，有`n*m`个`1*1`的单元格。每个单元格上的数字就是按照从1到n和1到m中的数的乘积。具体如下

```
n = 3, m = 3
1   2   3
2   4   6
3   6   9
```

给出一个查询的值k，求出按照这个方式列举的的数中第k大的值v。

```
例如上面的例子里，
从大到小为(9, 6, 6, 4, 3, 3, 2, 2, 1)
k = 1, v = 9
k = 2, v = 6
k = 3, v = 6
...
k = 8, v = 2
k = 9, v = 1
```

```
输入描述:
只有一行是3个数n, m, k 表示场地的宽高和需要查询的k。使用空格隔开。

输出描述:
给出第k大的数的值。
示例1
输入
3 3 4
输出
4

备注:
【数据范围】
100%的数据
1 <= n, m <= 40000
1 <= k <= n * m
30%的数据
1 <= n, m <= 1000
```

#### [题解链接](./solution_2.md)
