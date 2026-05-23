# 栈（Stack）

栈是一种 **后进先出（LIFO, Last In First Out）** 的数据结构：

```text
底
1
2
3
顶
```

先放进去的后出来：

```text
push(1)
push(2)
push(3)

pop()

得到：3
```

---

# 创建

```cpp
#include <stack>

stack<int> st;
stack<char> st;
stack<pair<int,int>> st;
```

---

# 常用操作

入栈：

```cpp
st.push(x);
```

出栈：

```cpp
st.pop();
```

查看栈顶：

```cpp
st.top();
```

判空：

```cpp
st.empty();
```

元素个数：

```cpp
st.size();
```

时间复杂度：

```text
push  O(1)
pop   O(1)
top   O(1)
```

---

# 注意

`pop()` 没有返回值：

错误：

```cpp
x=st.pop();
```

正确：

```cpp
int x=st.top();

st.pop();
```

访问前先判空：

```cpp
if(!st.empty()){

    cout<<st.top();
}
```
