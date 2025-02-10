# Linear List (线性表)

## 📌 Definition
A **Linear List** is a **finite sequence of elements** arranged in a **linear order**. Each element has a unique **predecessor** (except the first one) and a unique **successor** (except the last one).

### Key Characteristics:
- **Ordered structure**: Elements are stored in a specific sequence.
- **Finite length**: The number of elements is countable.
- **Single connection**: Each element (except the first and last) has one predecessor and one successor.

线性表元素的个数n（n≥0）定义为线性表的长度，当n=0时，称为空表。

描述顺序存储结构需要三个属性：
■　存储空间的起始位置：数组data，它的存储位置就是存储空间的存储位置。
■　线性表的最大存储容量：数组长度MaxSize。
■　线性表的当前长度：length

# Linear List Advantages & Disadvantages

# 线性表的优缺点

| **优点** | **缺点** |
|---------|---------|
| ✅ 无须为表示表中元素之间的逻辑关系而增加额外的存储空间 | ❌ 插入和删除操作需要移动大量元素 |
| ✅ 可以快速地存取表中任一位置的元素 | ❌ 当线性表长度变化较大时，难以确定存储空间的容量 |
|   | ❌ 可能造成存储空间的“碎片” |

# 头指针 vs 头结点

| **头指针** | **头结点** |
|------------|------------|
| 头指针是指向链表第一个结点的指针，若链表有头结点，则是指向头结点的指针 | 头结点是为了操作的统一和方便而设立的，放在第一元素结点之前，其数据域一般无意义（也可存放链表的长度） |
| 头指针具有标识作用，所以常用头指针冠以链表的名字 | 有了头结点，对在第一元素结点前插入结点和删除第一结点，其操作与其它结点的操作就统一了 |
| 无论链表是否为空，头指针均不为空。头指针是链表的必要元素 | 头结点不一定是链表必须要素 |

单链表的读取
1．声明一个结点p指向链表第一个结点，初始化j从1开始；
2．当j<i时，就遍历链表，让p的指针向后移动，不断指向下一结点，j累加1；
3．若到链表末尾p为空，则说明第i个元素不存在；
4．否则查找成功，返回结点p的数据


