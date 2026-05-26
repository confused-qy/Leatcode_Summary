# Heap（堆）

堆（Heap）是一种 **完全二叉树**，用于快速维护最大值或最小值。

分为：

```text
大根堆（Max Heap）
父节点 ≥ 子节点

小根堆（Min Heap）
父节点 ≤ 子节点
```

堆顶一定是当前最大值或最小值。

---

# C++中的堆

STL 使用：

```cpp
priority_queue<int> pq;
```

默认：

```text
大根堆
```

例如：

```cpp
pq.push(3);
pq.push(1);
pq.push(5);

pq.top()
```

结果：

```text
5
```

---

# 小根堆

```cpp
priority_queue<
    int,
    vector<int>,
    greater<int>
> pq;
```

堆顶：

```text
最小值
```

---

# 常用操作

加入：

```cpp
pq.push(x);
```

删除堆顶：

```cpp
pq.pop();
```

查看堆顶：

```cpp
pq.top();
```

判空：

```cpp
pq.empty();
```

元素个数：

```cpp
pq.size();
```

---

# 时间复杂度

```text
push      O(log n)

pop       O(log n)

top       O(1)
```

---

# 注意

`pop()` 没有返回值：

错误：

```cpp
x=pq.pop();
```

正确：

```cpp
x=pq.top();

pq.pop();
```

空堆不能：

```cpp
pq.top()
```

先：

```cpp
if(!pq.empty())
```

---

# 常见用途

Top K：

```cpp
维护大小为k的小根堆
```

第K大元素：

```cpp
priority_queue<
int,
vector<int>,
greater<int>
> pq;
```

图算法：

```text
Dijkstra
Prim
```

合并排序：

```text
Merge K Sorted Lists
```

---

# pair堆

默认先比较 first：

```cpp
priority_queue<pair<int,int>> pq;
```

例如：

```cpp
pq.push({5,2});

pq.push({3,10});
```

堆顶：

```text
(5,2)
```

---

# 自定义比较

```cpp
auto cmp=[](
pair<int,int>& a,
pair<int,int>& b){

    return a.second>b.second;
};

priority_queue<
pair<int,int>,
vector<pair<int,int>>,
decltype(cmp)
> pq(cmp);
```

---

一句话：

```text
堆 = 自动维护最大/最小值的数据结构
```