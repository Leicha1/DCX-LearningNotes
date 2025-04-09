# 1.'auto','auto &','const auto &'的区别

auto用于推断类型，具体可用于声明变量时根据初始化表达式自动推断该变量的类型，也就是可用在for循环。

也可以用于声明函数返回值的占位符。
- **auto** 
	auto用于copy一份集合中的数据，对于这种情况，在循环体中不论怎么修改copy的数据，是不会影响到原有集合中的数据的。
```cpp
int arr[5] = {0, 1, 2, 3, 4}; 
cout << "使用auto" << endl; 
for (auto a: arr) 
	{ a += 1; cout << a << "\t"; } 
cout << endl; 
cout << "原数组" << endl; 
for (int i = 0; i < 5; i++) 
	{ cout << arr[i] << "\t"; } 
cout << endl;	
//结果
//使用auto 
//1 2 3 4 5 
//原数组 
//0 1 2 3 4
```

- **auto &**
	auto &相当于获取一份集合中数据的引用，那么对于数据的修改，就会直接影响到集合数据本身。
```cpp
int arr[5] = {0, 1, 2, 3, 4}; 
cout << "使用auto" << endl; 
for (auto &a: arr) { 
	a += 1; 
	cout << a << "\t"; 
} 
cout << endl; 
cout << "原数组" << endl; 
for (int i = 0; i < 5; i++) 
	cout << arr[i] << "\t"; 
cout << endl;	
//结果
//使用auto 
//1 2 3 4 5 
//原数组 
//1 2 3 4 5 
```
- const auto &
	在auto &的前面加上了const修饰，意味着它会获取一份集合中数据的引用，但是只可以被读取，不能被修改。
# 数据类型转换
## **C++ 标准库转换函数**

### (1) `std::to_string`（数值 → 字符串）
```cpp
int num = 123;
std::string str = std::to_string(num);  // "123"
```
### (2) `std::stoi`, `std::stol`, `std::stod`,`std::stoll`（字符串 → 数值）
```cpp
std::string s = "3.14";
double d = std::stod(s);  // 3.14
```
### (3) `std::from_chars`（C++17，高性能字符串 → 数值）
```cpp
#include <charconv>
std::string s = "42";
int num;
std::from_chars(s.data(), s.data() + s.size(), num);  // num = 42
```
# 2.库函数
## warp（）
```cpp
//实现1
int tmp = s[i];
s[i] = s[j];
s[j] = tmp;
//实现2
s[i] ^= s[j];
s[j] ^= s[i];
s[i] ^= s[j];
```

# 3.STL
## 容器
### 1.vector
### 2.string
### 3.stack
### 4.queue
### 5.deque
### 6.set
### 7.map
### 8.list
### 9.优先级队列：priority_queue
构造：
```cpp
//默认构造大顶堆（堆头是最大元素）
priority_queue<int,vector<int>> pq;

//构造小顶堆需自行定义函数
// 小顶堆构造一
class mycomparison {
    public:
        bool operator()(const pair<int, int>& lhs, const pair<int, int>& rhs) {
            return lhs.second > rhs.second;
        }
    };
// 小顶堆构造二
struct mycompare{
        bool operator()(pair<int,int> &left,pair<int,int> &right){
            return left.second > right.second;
        }
    };
//小顶堆
priority_queue<pair<int, int>, vector<pair<int, int>>, mycomparison> pri_que;
priority_queue<pair<int, int>, vector<pair<int, int>>, mycompare> pri_que;
```

