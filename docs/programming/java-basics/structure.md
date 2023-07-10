# 结构

## 结构

一个合法的 Java 程序必须写在一个名为「类」的结构中。「类」的声明如下：

```java
public class Example {
    // ...
}
```

由于 Java 是一门 「面向对象语言」，在代码编写过程中我们的代码都是写在类中的。在类中，我们可以声明变量、方法等。
```java
public class Example {
    public int a;
    public String b = "abc";
    
    public void print() {
        System.out.println("Hello World!");
    }
```

## 入口

Java 程序的入口是 `main` 方法。`main` 方法的声明如下：

```java
public static void main(String[] args) {
    // ...
}
```
需要注意的是，`main` 方法必须完全与以上一致，否则编译器无法发现。

## 注释

Java 中的注释有三种：
- 单行注释：`// ...`
- 多行注释：`/* ... */`
- 文档注释：`/** ... */`

其中，文档注释是一种特殊的注释，可以被编译器识别并生成文档。比如：

```java
/**
 * This is a doc comment.
 */
public class Example {
    // ...
}
```