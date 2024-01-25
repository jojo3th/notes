多态 --> 花木兰替父从军

多态的本质就是父类的引用可以指向子类

向上转型 ：class Animal   class Cat extends Animal

Animal animal = new Cat();

编译类型为Animal,编译器认为这是一个Animal

运行类型为Cat,java 认为这是一个Cat

所以这个animal可以调用Animal类的所有方法,但是不可以调用cat中特有的方法,猜测java中可以调用的方法由编译器管 javac

实际的方法是哪一个由java管,也就是说这里的方法调用符合继承关系中子类调用方法的规则

向下转型 ：Cat cat = (Cat)animal;

这个时候cat变成了真正的cat，花木兰打仗打完了，又变成了花木兰

举例一个多态的应用例子：

public void feed(Animal animal, Food food)

此时Animal的所有子类都可以传进来（前提是访问修饰符没有问题）

这样的话就可以不用为每一个类都写一个类似的函数了

***属性调用看编译类型，方法调用用运行类型***

jvm 栈， 堆， 方法区

编译时多态：overload

运行时多态：override