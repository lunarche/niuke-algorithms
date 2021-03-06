## day 04 

### 1. [百分号解码](<https://www.nowcoder.com/questionTerminal/79c892f6001b49d5a0680716e6f4f14d>)
来源：[深信服校园招聘算法练习卷](<https://www.nowcoder.com/test/23358504/summary>)

在URL字符串中，如果百分号%后面跟了两个十六进制数字，那么它表示相应ASCII值所对应的字符，如%2F表示'/'，%32表示'2'。%编码还可以进行嵌套，如%%32F可以解码成%2F，再进一步解码成/。如果没有任何百分号后面跟的是两个十六进制数字则无法再进行解码。

现在有一系列的URL，小强希望你帮忙进行百分号解码，直到无法再解码为止。

```
输入描述:
第一行一个正整数T（T<=10），表示T个测试样例；
对于每个测试样例，
输入字符串s，字符串不包含空白符且长度小于100,000。

有部分测试样例的字符串长度<=1,000。

输出描述:
输出T行，每行一个字符串，表示解码后的结果。
示例1
输入
1
%%32F
输出
/
```

#### [题解链接](./solution_1.md)

### 2. [子数组查找](<https://www.nowcoder.com/questionTerminal/4406e29ed847446e9745d75f43fad3fe>)

来源：[深信服校园招聘算法练习卷](<https://www.nowcoder.com/test/23358504/summary>)

给定长度为N的整数数组，以及M个互不相同的整数，请找出包含这M个整数的最短子数组。

例如：给定数组[4 2 1 3]，包含数字集{2, 3}的最短子数组是[2 1 3]，包含数字集{1, 3}的最短子数组是[1 3]。

```
输入描述:
第一行一个正整数T（T<=10），表示T个测试样例；
对于每个测试样例，
输入正整数N（N<=100,000），表示数组长度；
接下来输入N个正整数，所有整数都>=0且<=1,000,000,000；
输入正整数M（M<=N），表示M个互不相同的整数；
接下来输入M个整数，表示要查询的整数，已保证互不相同。

有部分测试样例满足N<=1,000。

输出描述:
输出T行，每行一个正整数，表示最短子数组的长度。如果不存在，输出0
示例1
输入
1
4
4 2 1 3
2
2 3
输出
3
```

#### [题解链接](./solution_2.md)