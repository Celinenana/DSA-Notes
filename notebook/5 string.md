# 字符串（String）

## 定义
**字符串**是由零个或多个字符组成的有限序列。字符串又被称为**字符序列**或**字符数组**。在计算机科学中，字符串是一种基本的数据结构，常用于表示文本信息。

## 基本概念
- **字符（Character）**：字符串的基本组成单位，可以是字母、数字、符号等。
- **长度（Length）**：字符串中字符的个数。长度为 0 的字符串称为**空字符串**。
- **子串（Substring）**：字符串中连续的一段字符序列。
- **前缀（Prefix）**：从字符串开头到某个位置的子串。
- **后缀（Suffix）**：从某个位置到字符串末尾的子串。

## 字符串的表示
在大多数编程语言中，字符串可以用以下方式表示：
- 使用双引号：`"Hello, World!"`
- 使用单引号：`'Hello, World!'`（在某些语言中）
- 使用反引号：`` `Hello, World!` ``（在某些语言中，如 JavaScript 的模板字符串）

## 常见操作
1. **拼接（Concatenation）**：将两个字符串连接在一起。
   - 示例：`"Hello" + " " + "World"` 结果为 `"Hello World"`

2. **查找（Search）**：在字符串中查找某个子串或字符。
   - 示例：在 `"Hello World"` 中查找 `"World"`，返回其起始位置。

3. **替换（Replace）**：将字符串中的某个子串替换为另一个子串。
   - 示例：将 `"Hello World"` 中的 `"World"` 替换为 `"DSA"`，结果为 `"Hello DSA"`。

4. **分割（Split）**：根据指定的分隔符将字符串分割成多个子串。
   - 示例：将 `"Hello,World,DSA"` 按 `,` 分割，结果为 `["Hello", "World", "DSA"]`。

5. **大小写转换（Case Conversion）**：将字符串中的字符转换为大写或小写。
   - 示例：将 `"Hello"` 转换为大写，结果为 `"HELLO"`。

## 字符串的存储
- **定长存储**：字符串的长度固定，超出部分会被截断。
- **变长存储**：字符串的长度可以动态变化，通常使用指针或动态数组实现。

## 字符串的应用
- **文本处理**：如搜索、替换、格式化等。
- **数据解析**：如解析 JSON、XML 等格式的数据。
- **密码学**：如哈希函数、加密算法等。

## 示例代码
```python
# Python 示例
s = "Hello, DSA!"
print(s)               # 输出: Hello, DSA!
print(len(s))          # 输出: 11
print(s[7:10])         # 输出: DSA
print(s.replace("DSA", "World"))  # 输出: Hello, World!

class StringADT:
    def __init__(self, chars=None):
        """初始化字符串。如果提供了字符序列，则生成对应的字符串。"""
        if chars is not None:
            self.data = list(chars)
        else:
            self.data = []

    def str_assign(self, chars):
        """生成一个其值等于字符串常量 chars 的串。"""
        self.data = list(chars)

    def str_copy(self, other):
        """由串 other 复制得当前串。"""
        self.data = other.data.copy()

    def clear_string(self):
        """将串清空。"""
        self.data = []

    def string_empty(self):
        """若串为空，返回 True，否则返回 False。"""
        return len(self.data) == 0

    def str_length(self):
        """返回串的元素个数，即串的长度。"""
        return len(self.data)

    def str_compare(self, other):
        """
        比较当前串与 other 串。
        若当前串 > other 串，返回值 > 0；
        若当前串 = other 串，返回 0；
        若当前串 < other 串，返回值 < 0。
        """
        if self.data > other.data:
            return 1
        elif self.data == other.data:
            return 0
        else:
            return -1

    def concat(self, s1, s2):
        """用当前串返回由 s1 和 s2 联接而成的新串。"""
        self.data = s1.data + s2.data

    def substring(self, pos, length):
        """
        返回当前串的第 pos 个字符开始，长度为 length 的子串。
        注意：pos 从 1 开始计数。
        """
        if 1 <= pos <= len(self.data) and 0 <= length <= len(self.data) - pos + 1:
            return ''.join(self.data[pos - 1:pos - 1 + length])
        else:
            raise ValueError("Invalid position or length")

    def index(self, t, pos):
        """
        若主串中存在和串 t 值相同的子串，则返回它在主串中第 pos 个字符之后第一次出现的位置，否则返回 -1。
        注意：pos 从 1 开始计数。
        """
        if pos < 1 or pos > len(self.data):
            raise ValueError("Invalid position")
        main_str = ''.join(self.data[pos - 1:])
        sub_str = ''.join(t.data)
        idx = main_str.find(sub_str)
        if idx != -1:
            return pos + idx
        else:
            return -1

    def replace(self, t, v):
        """
        用 v 替换主串中出现的所有与 t 相等的不重叠的子串。
        """
        main_str = ''.join(self.data)
        sub_str = ''.join(t.data)
        replace_str = ''.join(v.data)
        self.data = list(main_str.replace(sub_str, replace_str))

    def str_insert(self, pos, t):
        """
        在当前串的第 pos 个字符之前插入串 t。
        注意：pos 从 1 开始计数。
        """
        if 1 <= pos <= len(self.data) + 1:
            self.data = self.data[:pos - 1] + t.data + self.data[pos - 1:]
        else:
            raise ValueError("Invalid position")

    def str_delete(self, pos, length):
        """
        从当前串中删除第 pos 个字符开始，长度为 length 的子串。
        注意：pos 从 1 开始计数。
        """
        if 1 <= pos <= len(self.data) and 0 <= length <= len(self.data) - pos + 1:
            self.data = self.data[:pos - 1] + self.data[pos - 1 + length:]
        else:
            raise ValueError("Invalid position or length")


def compute_lps_array(pattern):
    """
    计算模式串的部分匹配表（LPS 数组）。
    LPS[i] 表示 pattern[0:i] 的最长相等前缀和后缀的长度。
    """
    length = 0  # 当前最长相等前缀和后缀的长度
    lps = [0] * len(pattern)  # 初始化 LPS 数组
    i = 1  # 从 pattern 的第二个字符开始

    while i < len(pattern):
        if pattern[i] == pattern[length]:
            length += 1
            lps[i] = length
            i += 1
        else:
            if length != 0:
                length = lps[length - 1]
            else:
                lps[i] = 0
                i += 1
    return lps


def kmp_search(text, pattern):
    """
    使用 KMP 算法在文本串 text 中查找模式串 pattern。
    返回 pattern 在 text 中第一次出现的位置，如果未找到则返回 -1。
    """
    n = len(text)
    m = len(pattern)

    if m == 0:
        return 0  # 空模式串总是匹配

    lps = compute_lps_array(pattern)  # 计算 LPS 数组
    i = 0  # text 的索引
    j = 0  # pattern 的索引

    while i < n:
        if text[i] == pattern[j]:
            i += 1
            j += 1

            if j == m:  # 完全匹配
                return i - j  # 返回匹配的起始位置

        else:
            if j != 0:
                j = lps[j - 1]  # 回退到 LPS 表中的位置
            else:
                i += 1  # 继续匹配下一个字符

    return -1  # 未找到匹配


```
