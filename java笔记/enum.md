# 枚举

#### 1不用enum关键字实现枚举

直接上代码：

```java
public class Season {
    private String name;
    private String figure;
    
    public static final Season SPRING = new Season("Spring", "warm");
    public static final Season SUMMER = new Season("Summer", "hot");
    public static final Season AUTUMN = new Season("Autumn", "gold");
    public static final Season WINTER = new Season("Winter", "warm");
    
    private Season(String name, String figure) {
        this.name = name;
        this.figure = figure;
    }
}
```

和单例设计模式有点像，就是将构造器改为私有的，在给外界提供几个static常量(*为什么是static? 因为Season不能被new*)

使用方法:

```java
Season spring = Season.SPRING;
```

#### 2用enum关键字实现枚举

直接上代码:

```java
public enum Season {
    SPRING("Spring", "warm"), SUMMER("Summer", "hot"), 
    AUTUMN("Autumn", "gold"), WINTER("Winter", "warm");
    private String name;
    private String figure;
    
    private Season(String name, String figure) {
        this.name = name;
        this.figure = figure;
    }
}
```

这个方式在底层和上面的差不多

***注意***：

1. 不同常量之间用`,`隔开
2. 枚举对象必须放在第一行（最前面）

enum枚举类隐式的继承了Enum类，所以enum枚举类不可以再继承其他类，但是枚举类还是一个类，类可以有的东西它也可以有。