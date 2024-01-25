动态绑定：
1.在java中方法总会和对象的运行类型绑定到一起（内存空间）
2.属性没有动态绑定机制，在哪里调用就用哪里的,跟作用域有关



通俗理解：当一个类调用方法时总是先在自己的类里找，找不到再找父类的

For an example：
```java
class Poo {
    private String shape;
	private int number = 3;

	public int getNumber() {
		return this.number;
	}
	public void moreFeces() {
		this.number += 3;
	}
	
	public int moreShit() {
		return getNumber() + 5;
	}
	
	public int morePoo() {
		return number + 5;
	}

}

class Shit extends Poo {
    private String shape;
	private int number = 5;

	public int getNumber() {
		return this.number;
	}
	public void moreFeces() {
		this.number += 3;
	}

}

public static void main(String[] args) {
	Poo poo = new Shit();

	System.out.println(poo.getNumber());//将会输出5
	System.out.println(poo.moreShit()); //将会输出10
	System.out.println(poo.morePoo());  //将会输出8

}
```