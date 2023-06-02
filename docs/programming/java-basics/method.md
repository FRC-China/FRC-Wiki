# 方法

## 声明

在 Java 中，「方法」类似于其他语言中的函数。其声明如下：

```java
// 修饰符 返回值类型 方法名(参数列表) { ... }
public void print() {
    // ...
    // Optional: return 返回值;
}
```
在方法中你可以包含各种逻辑，比如变量声明、循环、判断等。

## 调用

在 Java 中，调用方法需要使用「对象.方法名(参数列表)」的形式。比如：

```java
public class Example {
    public void print() {
        System.out.println("Hello World!");
    }
}
public class Main {
    public static void main(String[] args) {
        Example example = new Example();
        example.print();
    }
}

// Output: Hello World!
```

## 参数

在 Java 中，方法的参数列表是用逗号分隔的。比如：

```java
public class Example {
    public void print(String str) {
        System.out.println(str);
    }
}
public class Main {
    public static void main(String[] args) {
        Example example = new Example();
        example.print("Hello World!");
    }
}

// Output: Hello World!
```