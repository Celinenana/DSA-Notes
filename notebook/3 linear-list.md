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

note：若线性表需要频繁查找，很少进行插入和删除操作时，宜采用顺序存储结构。若需要频繁插入和删除时，宜采用单链表结构。
当线性表中的元素个数变化较大或者根本不知道有多大时，最好用单链表结构，这样可以不需要考虑存储空间的大小问题。

# 链表类型（Types of Linked Lists）

在数据结构中，**链表（Linked List）** 是一种线性数据结构，其中元素（节点）按顺序存储，并且每个节点包含一个指向下一个节点的指针。根据链表的存储方式和特性，可以将链表分为以下几种类型：

## 1. 单链表（Singly Linked List）
**定义：**  
单链表是最基本的链表类型，每个节点包含两个部分：
- **数据（Data）**：存储节点的值。
- **指针（Pointer）**：指向链表中的下一个节点。

**特点：**
- 只能从头部（head）遍历到尾部（tail）。
- 插入和删除操作相对简单，但无法直接访问前一个节点。

**示例结构：**

Head → Node1 → Node2 → Node3 → None


## 2. 静态链表（Static Linked List）
**定义：**  
静态链表使用数组来存储链表元素，同时维护一个“游标（cursor）”指向下一个节点的索引，而不是使用指针。

**特点：**
- 适用于无法动态分配内存的情况，如某些嵌入式系统。
- 由于使用数组实现，空间的分配相对固定，不如动态链表灵活。

**示例结构：**
Index Data Next 0 A 2 1 - - 2 B 3 3 C -1 (end)

## 3. 循环链表（Circular Linked List）
**定义：**  
循环链表是一种特殊的链表，其中最后一个节点指向第一个节点，而不是指向 `None`，形成一个闭环。

**特点：**
- 没有 `NULL` 结尾，可以从任意位置遍历整个链表。
- 适用于循环队列、任务调度等应用。

**分类：**
- **单向循环链表（Singly Circular Linked List）**：
Head → Node1 → Node2 → Node3 → Head

- **双向循环链表（Doubly Circular Linked List）**：
Head ↔ Node1 ↔ Node2 ↔ Node3 ↔ Head

## 4. 双向链表（Doubly Linked List）
**定义：**  
双向链表是每个节点都包含两个指针的链表：
- **前驱指针（Prev）**：指向前一个节点。
- **后继指针（Next）**：指向下一个节点。

**特点：**
- 可以在 **O(1)** 时间复杂度内向前或向后遍历，提高了查找效率。
- 适用于需要频繁插入和删除的场景，如文本编辑器的撤销操作。

**示例结构：**
None ← Node1 ↔ Node2 ↔ Node3 → None


## 总结（Summary）
| 类型 | 方向 | 是否循环 | 适用场景 |
|------|------|---------|---------|
| **单链表** | 只能向前 | 否 | 基本存储结构 |
| **静态链表** | 只能向前 | 否 | 受限环境，如嵌入式系统 |
| **循环链表** | 只能向前或双向 | 是 | 任务调度、循环队列 |
| **双向链表** | 可以向前和向后 | 可选 | 频繁插入删除，如文本编辑器 |

链表是一种强大的数据结构，每种类型都有其适用的场景。在选择链表时，需要根据实际应用需求做出最佳决策。




