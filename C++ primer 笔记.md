# C++ primer 笔记

[TOC]

原书扩展示例源代码地址：http://www.informit.com/title/0321714113



## 第一章

nothing

## 第二章 变量

```c++
//c++初始化的不同形式
int units_sold = 0;
int units_sold = {0};
int units_sold{0}; 
int units_sold(0);
//{} c++11 使用{}进行初始化时，如果存在丢失信息的风险，则编译器报错
double ld = 3.1415;
int a{ld};  //error!
int c(ld);  //正确但丢失了部分信息
```

### 声明和定义

声明一个变量而非定义，关键字 extern

```c++
extern int i;    //声明i而非定义
int j;           //声明并定义j
```

变量能且只能被定义一次，但是可以被多次声明。

多个文件中使用一个变量，只有一个文件可以定义，其他的都需要声明。

### 作用域

```c++
#include<iostream>
using namespace std;
int main(){
	int i=100,sum=0;
	for(int i=0;i<10;i++)
	    sum+=i;
	cout<<sum<<" "<<i;
	return 0;
} //执行结果为45 100 但最好不要这么做
```

### 引用

变量的别名 ‘&’ ，对别名的操作也会应用到原变量名上，实际上就是一个变量

### 指针

指针与引用的区别：指针本身就是一个对象，而引用只是一个别名，和引用的对象绑定在一起。且指针在定义时不是必须初始化，引用则不然。

```c++
int ival=42;
int *p = &ival;
cout<<*p;  //42 p是ival的地址 或是指向变量ival的指针


int i=42;
int *pi = 0;
int *pi2 =&i;
int *pi3;

pi3=pi2; //pi3和pi2指向同一个对象
pi2=0;
```

#### void*指针

void*是一种特殊类型指针，可以存放任意对象的地址。

### const的引用与指针 （常量

允许const int&等绑定到普通int对象上。效果是const绑定在临时量对象上，不允许通过const引用修改普通对象。

指针与引用基本同理。不允许通过指针改变指向的对象

### 类型别名

typedef 定义类型别名 同义词。

### auto类型说明符 c++11

略

### decltype类型指示符 c++11

选择并返回操作数的数据类型

``` c++
decltype(f()) sum = x ; //sum的类型就是函数f的返回类型
```

### struct



## 第三章 字符串、向量和数组

### string

string 的初始化

```c++
string temp(10,'c');   //cccccccccc
```

字符串处理

cctype头文件函数

```c++
p82
```

c++版本的c标准库去掉.h前面加上c 比如cmath cctype



```c++
//范围for语句
for(declaration : expression)
//declaration 是类型 expression是一个序列，也可以是数组或vector
string str="ksjdflkajf";    
for(auto c :str)
    cout<<c<<endl;
```

### vector



### 迭代器

iterator

获取迭代器的一种方法

```c++
vector<int> s=(10,5);
auto it=s.begin();
vector<int>::iterator it_s;
*it = toupper(*it);//迭代器也像指针一样 解引用然后获取所指示的元素并操作
++it;
//由于end()不是最后一个元素 所以不能直接将迭代器=end()来进行++ —— 但是可以*（--s.end())来引用最后一个
```

tips：泛型编程，stl尽量使用迭代器而不是下标，因为所有容器都有迭代器但不是都有下表，通过迭代器的！=判定可以提高通用性。

### c++与旧代码的接口

 p111页

tips：尽量使用标准库类型而非数组



### 多维数组

```c++
int ia[5][5];
//使用范围for语句处理多维数组
for(auto &row :ia)
    for(auto *col : row){
        col=cnt;
        ++cnt;
    }
```

## 第四章

😁改天再说

