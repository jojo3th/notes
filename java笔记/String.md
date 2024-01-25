```java
String str1 = "hit";
String str2 = "hit";
System.out.ptintln(str1 == str2);
System.out.ptintln(str1.equals(str2));
```

**true, true**

```java
String str1 = "HIT";
String str2 = new String("HIt");
```

这两种创建方式不同，第一行**str1**指向的是常量池的`”HIT“`，第二行**str2**指向的是堆中的一个空间，而堆中的**String**引用指向常量池中的`”HIT“`

```java
String str = "Hello" + "world";
String str1 = "Hello";
String str2 = "World";
String str3 = str1 + str;
```

第一句和第四句在底层是不同的，可以用**debug**查看

就结果来说**1**的结果是**str**指向常量池的**“HelloWorld”**

**2**的结果为**str3**指向一个堆中的**String**对象

而且在**1**创建的时候，编译器发现`“Hello”`和`“World”`没有引用指向，所以1等价于`String str = "HelloWorld"`

