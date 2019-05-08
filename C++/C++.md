 C++

# 内存布局

## 虚指针

### 引入虚指针为每一个对象节省空间，所有同一个类的对象共享一份虚表，存在rodata区，否则每一个对象需要维护一个自身的虚表。

## 多重继承

### 按声明的继承顺序，有虚表的优先排，再是没虚表的，继承类对象放后面，但其自身拥有的虚表项被拼接在第一个虚表后。虚指针放0偏移量位置(VC++)

# 基本语法

## 四种类型转换

### static_cast

### const_cast

### dynamic_cast

### reinterpret_cast

## const的使用

## static

### 修饰普通变量

### 修饰普通函数

### 修饰成员变量

### 修饰成员函数

## volatile

### volatile 关键字声明的变量，每次访问时都必须从内存中取出值

## this

### this 指针被隐含地声明为: ClassName *const this

### const 成员函数中，this 指针的类型为：const ClassName* const

## inline

### 在类声明中定义的函数，除了虚函数的其他函数都会自动隐式地当成内联函数。

### inline virtual 唯一可以内联的时候是：编译器知道所调用的对象是哪个类（如 Base::who()），这只有在编译器具有实际对象而不是对象的指针或引用时才会发生。

## assert

### static_assert: compile time assert

## sizeof

### 对数组：得到数组所占空间的大小

### 对指针：得到指针的大小

## #pragma pack(n)

### 设定结构体、联合以及类成员变量以 n 字节方式对齐

## extern

### 用指定语言的符号修饰规则而不是C++的符号修饰规则，一般用作和C库的链接

## friend

### 可以访问声明了friend的类的私有成员

### 不可传递

### 单向

## using

### 派生类能够重用其直接基类定义的构造函数。

### using std::cout 引入特定的名称，避免使用using namespace std;

## enum

### unscoped enumeration: enum Color {red, green, yellow }; case red:

### scoped enumeration: enum class Color {red, green, yellow}; case Color::red:

## 成员初始化列表

### 少了一次调用默认构造函数的过程

### 有些必须使用的场合

#### 成员变量有引用类型

#### 成员对象未提供默认构造函数

#### 常量成员

## virutal

### 被继承的类的析构函数必须声明为虚函数

## new

### placement new

### new handler

## 重载决议

## ADL

#include <iostream>intmain(){std::cout<<"Test\n";// There is no operator<< in global namespace, but ADL// examines std namespace because the left argument is in// std and finds std::operator<<(std::ostream&, const char*)operator<<(std::cout,"Test\n");// same, using function call notation // however,std::cout<<endl;// Error: 'endl' is not declared in this namespace.// This is not a function call to endl(), so ADL does not apply  endl(std::cout);// OK: this is a function call: ADL examines std namespace// because the argument of endl is in std, and finds std::endl (endl)(std::cout);// Error: 'endl' is not declared in this namespace.// The sub-expression (endl) is not a function call expression}

## ODR(One Definition Rule)

# 模板

## 模板特化，偏特化

## CRTP(Curiously Recurring Template Pattern)

## SFINAE(Substitution Failure Is Not An Error)

### https://zh.cppreference.com/w/cpp/language/sfinae

# 标准库

## 标准库中的容器，常见的实现方式和常见操作的复杂度

### 顺序容器

#### std::vector

##### 容量增长的机制

##### push_back时间复杂度分析

#### std::array

#### std::forward_list

#### std::list

### 关联容器

#### 有序关联容器

##### std::set

##### std::map

##### std::multiset

##### std::multimap

#### 无序关联容器

##### std::unordered_set

##### std::unordered_map

##### std::unordered_multiset

##### std::unordered_multimap

### 容器适配器(Container Adaptor)

#### std::stack

#### std::queue

#### std::priority_queue

### Iterator Invalidation

# 现代C++

## RAII

## 智能指针

### std::unique_ptr

### std::shared_ptr

#### shared_from_this

#### 循环引用： std:weak_ptr

## lambda

## 左值右值

### 右值引用： 右值引用就是必须绑定到右值（一个临时对象、将要销毁的对象）的引用，一般表示对象的值。

### std::move

### std::forward

### reference collapse

#### rvalue reference to rvalue reference collapses to rvalue reference, all other combinations form lvalue reference

#### rvalue reference variables are lvalues when used in expressions

### Forwarding references

#### 1) function parameter of a function template declared as rvalue reference to cv-unqualified type template parameter of that same function template: template<class T> int f(T&& x) {

#### 2) auto&& except when deduced from a brace-enclosed initializer list: auto&& vec = foo(); for (auto&& x: f()) {

# 并发

## 写一个线程池

## memory order

# 调用约定
