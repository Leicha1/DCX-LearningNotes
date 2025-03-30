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