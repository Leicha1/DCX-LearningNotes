# 1. 数据类型
![](https://cdn.jsdelivr.net/gh/Leicha1/tuchuang/img/20250312204032.png)
# 2. 关键字与标识符

### 关键字 (Keywords)

关键字是 Java 语言中预先定义的、具有特殊含义的单词。它们在语法中有特定的用途，不能用作标识符。Java 关键字都是小写的，常见的关键字包括：

- **数据类型**: `int`, `float`, `double`, `char`, `boolean`, `void`
- **流程控制**: `if`, `else`, `switch`, `case`, `default`, `while`, `do`, `for`, `break`, `continue`, `return`
- **访问控制**: `public`, `private`, `protected`
- **类与对象**: `class`, `new`, `this`, `super`, `instanceof`
- **异常处理**: `try`, `catch`, `finally`, `throw`, `throws`
- **修饰符**: `static`, `final`, `abstract`, `synchronized`, `volatile`, `transient`
- **包与导入**: `package`, `import`
- **其他**: `enum`, `assert`, `interface`, `extends`, `implements`
### 标识符 (Identifiers)

标识符是程序员为变量、方法、类、包等定义的名称。标识符必须遵循以下规则：

1. **组成**: 标识符可以由字母、数字、下划线 (`_`) 和美元符号 (`$`) 组成。
2. **开头**: 标识符必须以字母、下划线 (`_`) 或美元符号 (`$`) 开头，不能以数字开头。
3. **大小写敏感**: 标识符是大小写敏感的，例如 `myVar` 和 `myvar` 是两个不同的标识符。
4. **不能是关键字**: 标识符不能是 Java 的关键字。
5. **长度**: 标识符的长度没有限制，但建议使用有意义的名称，并保持简洁。
### 示例
- **合法的标识符**:
  - `myVariable`
  - `_myVar`
  - `$myVar`
  - `myVar1`
  - `MyClass`
- **非法的标识符**:
  - `1myVar` (以数字开头)
  - `my-Var` (包含非法字符 `-`)
  - `class` (关键字)
### 总结 
- **关键字**是 Java 语言中具有特殊含义的保留字，不能用作标识符。
- **标识符**是程序员定义的名称，用于标识变量、方法、类等，必须遵循命名规则。

# 3.方法
## 1.方法详解
	Java开发的软件，功能的最小单位是一个个的方法
![](https://raw.githubusercontent.com/Leicha1/tuchuang/main/img/20250312210036.png)
- 方法的完整定义格式

修饰符 返回值类型 方法名（形参）{
	方法体代码（需要执行的功能代码）
	return 返回值；
}
例：求两个整数的最大值
```
public static int max(int a,int b){
	int max = a > b ? a : b;
	return max;
}
```
## 2.方法的注意事项
1. 方法重载
- 一个类中，出现多个方法的名称相同，但是形参列表不同，那么这些方法称为方法重载
```
// 定义一个方法 打印一个整数  
public static void print(int a){  
    System.out.println(a);  
}  
// 定义一个重载方法 打印字符串  
public static void print(String str){  
    System.out.println(str);  
}  
// 定义一个重载方法 打印两个整数之和  
public static void print(int a, int b){  
    System.out.println(a + b);  
}
```
2. 无返回值的方法中，可以直接通过return，立即结束当前方法的执行；

# 4.类型转换
## 1 自动-强制类型转换
1. 自动类型转换
- 类型范围小的变量，可以直接赋值给类型范围大的变量
 ![](https://raw.githubusercontent.com/Leicha1/tuchuang/main/img/20250313132536.png)
2. 强制类型转换
- 类型范围大的变量，不可以直接赋值给类型范围小的变量，需要进行强制类型转换
![](https://raw.githubusercontent.com/Leicha1/tuchuang/main/img/20250313135609.png)
注意：
- 强制类型转换可能会出现数据溢出现象
## 2 表达式的自动类型提升
- 在表达式中，小范围类型的变量，会自动转换成表达式中较大范围的类型变量
![](https://raw.githubusercontent.com/Leicha1/tuchuang/main/img/20250313140420.png)
注意：
- 表达式的最终结果类型由表达式中范围最大类型决定
- ==在表达式中==，==byte、short、char==类型变量==直接转换为int==类型变量参与计算
# 5.输入输出
![](https://raw.githubusercontent.com/Leicha1/tuchuang/main/img/20250313143244.png)

使用Scanner接收用户从键盘输入的数据，需要以下步骤：
![](https://raw.githubusercontent.com/Leicha1/tuchuang/main/img/20250313143533.png)
# 6.运算符
