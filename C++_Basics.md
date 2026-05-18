# 目录
- [哈希表(hash table)](#哈希表)
- [字符串(string)](#字符串)
- 



# 哈希表
**hash table**

创建：
``` cpp
#include <unordered_map>

unordered_map<string,int> mp; //string是key，int是value
```

初始化：
``` cpp
unordered_map<string,int> mp{
	{"Tom" , 10} , {"Alice" , 20} , {"Jack" , 30}
};
```

插入/修改：
``` cpp
mp["Tom"] = 95;
```

判断key是否存在：
``` cpp
if (mp.find("Tom") != mp.end())
{
	cout << "exist" << endl;
}
```

删除：
``` cpp
mp.erase("Tom")
```

遍历：
``` cpp
for (auto& p : mp)
{
	cout << p.first << ":" << p.second << endl;
	// 此处p.first是key，p.second是value
}
```

获取大小:
``` cpp
mp.size();
```

检查是否为空：
``` cpp
mp.empty();
```

安全读取：
``` cpp
mp.at(key)
// 如果key不存在会直接报错。如果是mp[key]，不存在会自动创建key为0。
```


# 字符串
**string**

创建：
``` cpp
#include <string>

string s = "hello";
```

修改字符：
``` cpp
s[0] = 'H'; // 注意用单引号是字符，双引号是字符串
```

获取长度：
``` cpp
s.length();
s.size();
```

拼接字符串：
``` cpp
string a = "hello";
string b = "world";
string c = a + b;
c = a + " " + b; //添加空格
```

遍历字符串：
``` cpp
for (int i = 0; i < s.length(); i++)
{
	cout << s[i] << endl;
}

for (char c : s)
{
	cout << c << endl;
}
```

添加/删除字符：
``` cpp
s.push_back('a');
s.pop_back();
```

检查是否为空：
``` cpp
s.empty();
```

取子串：
``` cpp
string s = "abcdef";
cout << s.substr(2,3); // 从下标2开始，长度3。会得到cde
```

查找字符串：
``` cpp
if (s.find("abc") != string::npos); // 说明找到了
```

替换：
``` cpp
string s = "hello";
s.replace(1,2,"xx"); // 从下标1开始，长度2。得到hxxlo
```

反转字符串：
``` cpp
reverse(s.begin(), s.end());
```

排序字符串：
``` cpp
sort(s.begin(), s.end());
```

