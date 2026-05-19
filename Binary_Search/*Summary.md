# 二分查找（Binary Search）

二分查找适用于 **有序数组**。核心思想是：每次取中间位置进行比较，并排除一半不可能的范围。

初始时：
```text
left = 0
right = n-1
```

循环执行：
```text
mid = left + (right-left)/2
```

比较 `nums[mid]` 和 `target`：
- 若 `nums[mid] == target`
  找到目标，直接返回。
- 若 `nums[mid] < target`
  目标只能在右边：
```text
left = mid + 1
```
- 若 `nums[mid] > target`  
  目标只能在左边：
```text
right = mid - 1
```
不断缩小搜索范围：
```text
[left, right]
↓
缩小一半
↓
再缩小一半
```
直到：
```text
left > right
```
说明目标不存在。

时间复杂度：

```text
O(log n)
```