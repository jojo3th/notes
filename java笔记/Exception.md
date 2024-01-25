异常都是Throwable的子类

分为Error Exception

Exception

分为编译异常和运行异常

编译异常例子：IOException， RuntimeException...

运行异常 :ArithmeticException, ArrayIndexOutOfBoundsException...

编译异常强制要求处理

运行时异常有自动处理 :throws

throws vs try catch finally

throws 踢皮球, 要么踢到JVM要么在某个方法中用try catch处理, 子类在重写时,异常必须是父类方法异常的子类或不变