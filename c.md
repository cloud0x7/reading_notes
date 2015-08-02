《C程序设计》
=============================

### 作者
    谭浩强 

### 简介


### 豆瓣链接
  [豆瓣链接](http://book.douban.com/subject/1679623/)

### 目录


### 内容



#### 最简单的C程序
    #include <stdio.h>
    int main()
    {
         printf("Hello World!\n");
         return 0;
    }

* 每一个C程序都必须有一个main函数。程序总是从main函数开始执行。
* C99建议把main函数指定为int……当主函数正常结束时，函数值为0，当出现异常或错误时，函数值为一个非0的整数。这个函数值是返回给调用main函数的操作系统的。
* C99正式将//注释纳入C语言新标准


#### C程序运行步骤
* 对源代码进行编译：作用是对源程序进行检查判断有无语法错误，并转换为二进制目标程序(.obj)
* 连接处理：连接目标文件及函数库，生成exe程序
* 运行


#### 3.2 数据的表现形式及其运算
* 常量
    - 整型常量：1000， 123， 0
    - 实型常量：12.23e3
    - 字符常量
        - 普通字符：单引号，只能是一个字符
        - 转义字符：
    - 字符串常量：
    - 符号常量： #define PI 3.14。不占内存，只是一个临时符号，预编译时进行字符替换的，编译后不存在
* 变量：必须先定义，后使用
* 常变量： const int a = 3;
* 标识符：


#### 数据类型
* 基本类型（*是C99增加的）
    - 整型类型
        - 基本整型 int
        - 短整型   short int
        - 长整型   long int
        - 双长整型 long long int *
        - 字符型   char
        - 布尔型   bool *
    - 浮点类型
        - 单精度浮点型 float
        - 双精度浮点型 double
        - 复数浮点型   float_complex, double_comple, long long_comple
* 枚举类型 enum
* 空类型   void
* 派生类型
    - 指针类型 *
    - 数组类型 []
    - 结构体类型 struct
    - 共用体类型 union
    - 函数类型
* 有符号整型数据存储单元中最高位代表符号（0为正，1为负）；无符号整型数据用"%u"格式输出
* 在输出字符变量的值时，可以选择以十进制整数形式输出 %d，或以字符形式输出 %c
> C标准没有具体规定各种类型数据所占用存储单元的长度，这是由各编译系统自行决定的。
> C标准只要求long型数据长度不短于int型，short型不长于int型


### 指针
* 地址指向变量单元，称为指针，通过它能找到以它为地址的内存单元
* 一个变量的地址称为该变量的“指针”
* 定义 int * point_1，其中“＊”表明为指针类型
* 一个变量的指针的含义包括两个方面，一是以存储单元编号表示的地址，一是它指向的存储单元的数据类型
* 指针是一个地址，而指针变量是存放地址的变量
* 定义指针变量时必须指定基类型，才能按存储单元长度及存储形式正确读取数据* 
* 指向函数的指针（可以用来实现多态）
  - int max(int, int);
  - int (* p)(int, int);
  - p = max;
* & 指向地址； * 指向地址的值（内容）
* 指针的运算
  - 如果指针变量p已指向数组中的一个元素，则p+1指向同一数组中下一个元素
* 返回指针值的函数
* 动态内存分配与指向它的指针变量
  - malloc, calloc, free, realloc


#### 动态内存分配
* 用于存放随时开辟，随时释放的数据的自由存储区，称为堆(heap)区
* malloc, calloc, free, realloc


#### 用户自己建立数据类型
* 结构体 struct Student {int num; char name[20]; int age; char sex;} s1, s2 = { 1, 'bob', 20, 1};
* 指向运算符 p->num 等同于 (* p).num
* 共用体类型
  - 不同变量共享同一段内存的结构
  - union Data {int i; char ch; float f;} a, b, c
  - 所占内存长度等于最长的成员的长度
  - 同一时间只能存放一个成员
  - union Data a = {16}
  - union Data a = {.ch='j'}
* 枚举类型
  - enum Weekday{sun,mon,tue,wed,thu,fri,sat};
* 声明新类型名 typedef
