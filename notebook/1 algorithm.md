## 算法：

算法是解决特定问题求解步骤的描述，在计算机中表现为指令的有限序列，并且每条指令表示一个或多个操作。

# 算法的特性：

1. 有穷性：算法在执行有限步后，自动结束而不会出现无限循环，并且每一个步骤在可接受的时间内完成。
2. 确定性：算法的每一步骤都具有确定的含义，不会出现二义性。
3. 可行性：算法的每一步都必须是可行的，即每一步都能够通过执行有限次数完成。
4. 输入：一个算法可以有零个或多个输入。
5. 输出：一个算法可以有一个或多个输出。

example:

```python
def sum(a, b):
    return a + b
```

好的算法：
A good algorithm should have the characteristics of correctness, readability, robustness, high efficiency, and low storage requirements.

事前分析估算方法：在计算机程序编制前，依据统计方法对算法进行估算。
消耗的时间取决于下列因素：
1．算法采用的策略、方法。
2．编译产生的代码质量。
3．问题的输入规模。
4．机器执行指令的速度。

## Algorithm Time Complexity Analysis

### First Algorithm:
```c
int i, sum = 0, n = 100;  /* Executes once */
for (i = 1; i <= n; i++)  /* Executes n+1 times */
{
    sum = sum + i;  /* Executes n times */
}
printf ("%d", sum);  /* Executes once */
```
**Time Complexity:** O(n)

---

### Second Algorithm:
```c
int sum = 0, n = 100;  /* Executes once */
sum = (1 + n) * n / 2; /* Executes once */
printf ("%d", sum);  /* Executes once */
```
**Time Complexity:** O(1)

---

### Extended Example:
```c
int i, j, x = 0, sum = 0, n = 100;  /* Executes once */
for (i = 1; i <= n; i++)  /* Executes n+1 times */
{
    for (j = 1; j <= n; j++)  /* Executes n*n times */
    {
        x++;
        sum = sum + x;
    }
}
```
**Time Complexity:** O(n²)


函数的渐近增长：给定两个函数f（n）和g（n），如果存在一个整数N，使得对于所有的n > N，f（n）总是比g（n）大，那么，我们说f（n）的增长渐近快于g（n）

判断一个算法的效率时，函数中的常数和其他次要项常常可以忽略，而更应该关注主项（最高阶项）的阶数。
