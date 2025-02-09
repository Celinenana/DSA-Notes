# 时间复杂度（Time Complexity）

## 📌 什么是时间复杂度？ | What is Time Complexity?
**时间复杂度**是衡量算法**运行时间增长速度**的数学表示，通常用**大 O 记号（Big-O Notation）**表示。它描述了输入数据规模 **n** 变化时，算法执行步骤的增长趋势。

**Time Complexity** is a mathematical notation that describes the **growth rate of an algorithm's execution time** as the input size **n** increases. It is commonly represented using **Big-O Notation**.

---

## 🕒 **常见时间复杂度** | Common Time Complexities
| **复杂度 (Complexity)** | **描述 (Description)** | **示例 (Example)** |
|-----------------|--------------------------------|-----------------|
| `O(1)` | **常数时间**，输入规模不影响时间 | 数组索引访问 |
| `O(log n)` | **对数时间**，数据量增加时，增长较慢 | 二分查找 |
| `O(n)` | **线性时间**，数据量翻倍，时间翻倍 | 遍历数组 |
| `O(n log n)` | **线性对数时间**，常见于高效排序算法 | 归并排序、快速排序 |
| `O(n²)` | **平方时间**，嵌套循环 | 冒泡排序、选择排序 |
| `O(2ⁿ)` | **指数时间**，递归问题 | 斐波那契数列（递归） |
| `O(n!)` | **阶乘时间**，最慢增长 | 旅行商问题（TSP） |

---

## 📊 **时间复杂度对比图** | Complexity Growth Comparison
时间复杂度的增长趋势如下：
- **O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(2ⁿ) < O(n!)**
  
```plaintext
O(1)        → 🔹🔹🔹🔹🔹   (最优 Best)
O(log n)    → 🔹🔹🔹🔹🔹🔹
O(n)        → 🔹🔹🔹🔹🔹🔹🔹🔹
O(n log n)  → 🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹
O(n²)       → 🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹
O(2ⁿ)       → 🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹🔹

推导大O阶：
1.用常数1取代运行时间中的所有加法常数。
2.在修改后的运行次数函数中，只保留最高阶项。
3.如果最高阶项存在且不是1，则去除与这个项相乘的常数。
得到的结果就是大O阶。

## 🏷️ **示例代码（Example Code）**

示例代码 | Example Code
1️⃣ O(1) - 常数时间 | Constant Time

```python
def get_first_element(arr):
    return arr[0]  # 访问数组首元素，时间复杂度 O(1)
```

2️⃣ O(n) - 线性时间 | Linear Time
```python
def find_element(arr, target):
    for num in arr:
        if num == target:
            return True  # 遍历数组查找目标，O(n)
    return False
```
3️⃣ O(log n) - 对数时间 | Logarithmic Time
```python
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = left + (right - left) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1  # 二分查找，O(log n)
``` 
4️⃣ O(n²) - 平方时间 | Quadratic Time
```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]  # 冒泡排序，O(n²)
```
5️⃣ O(2ⁿ) - 指数时间 | Exponential Time
```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)  # 递归斐波那契，O(2ⁿ)
```

O(1)<O(logn)<O(n)<O(nlogn)<O(n2)<O(n3)<O(2n )<O(n!)<O(n^n)
