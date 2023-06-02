# 变量与类型

## 变量声明
```java
// 变量类型 变量名 = 变量值;
int a = 1;

/** 
 * 在 JDK 11 后，Java 引入了 var 特性。
 * 使得你可以不用手动写出变量类型，而是由编译器自动推断出变量类型。
 **/
var b = 1;
```

## 基础类型
Java 中的基础类型有 8 种，分别是：
- byte
- short
- int
- long
- float
- double
- boolean
- char

## 基础类型的包装类
Java 中的基础类型都有对应的包装类，包装类的作用是将基础类型包装成对象，使得基础类型具有对象的特性。关于对象，将在后续章节进行讲解。
```java
// 基础类型
int a = 1;

// 包装类
Integer b = 1;
```

## 基础类型的默认值
Java 中的基础类型都有默认值，如下：
- byte: 0
- short: 0
- int: 0
- long: 0L
- float: 0.0f
- double: 0.0d
- boolean: false
- char: '\u0000'

## 基础类型的转换
Java 中的基础类型可以相互转换，但是需要注意的是，当转换的类型范围较大时，可能会出现精度丢失的情况。
```java
// 从小到大转换
int a = 1;
long b = a;

// 从大到小转换
long c = 1L;
int d = (int) c;

// 精度丢失
double e = 1.0d;
int f = (int) e;
```

## 基础类型的运算
Java 中的基础类型可以进行运算，运算的结果也是基础类型。
```java
// 加法
int a = 1;
int b = 2;
int c = a + b;

// 减法
int d = 1;
int e = 2;
int f = d - e;

// 乘法
int g = 1;
int h = 2;
int i = g * h;

// 除法
int j = 1;
int k = 2;
int l = j / k;

// 取余
int m = 1;
int n = 2;
int o = m % n;
```

## 基础类型的比较
Java 中的基础类型可以进行比较，比较的结果是布尔类型。
```java
// 大于
int a = 1;
int b = 2;
boolean c = a > b;

// 小于
int d = 1;
int e = 2;
boolean f = d < e;

// 大于等于
int g = 1;
int h = 2;
boolean i = g >= h;

// 小于等于
int j = 1;
int k = 2;
boolean l = j <= k;

// 等于
int m = 1;
int n = 2;
boolean o = m == n;

// 不等于
int p = 1;
int q = 2;
boolean r = p != q;
```
