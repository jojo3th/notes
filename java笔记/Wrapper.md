# Wrapper

#### 1手动装箱

```java
int number = 10;
Integer integer = Integer.valueOf(number);
// 或者
Integer integer = new Integer(number);
```

#### 1手动拆箱

```java
Integer integer;
int number = integer.intValue();
```

jdk5 以后由自动装箱和拆箱

#### 2valueOf源码

```java
public static Integer valueOf(int i) {
    if (i >= IntegerCache.low && i <= IntegerCache.high)
        return IntegerCache.cache[i + (-IntegerCache.low)];
    return new Integer(i);
}
```

`IntegerCache.low` = -128, `IntegerCache.high` = 127.刚好是一个字节的范围

所以

```java
Integer number1 = 10;
Integer number2 = 10;
Integer number3 = 128;
Integer number4 = 128;
int number = 128;
System.out.println(number1 == number2);
System.out.println(number3 == number4);
System.out.println(number3 == number5);
```

输出为 **true false true**

只要 **==** 运算符左右有基本数据类型，**==**就是判断值是否相等