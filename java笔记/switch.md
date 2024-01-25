switch（x）
{
	case ‘y’：，
}

x 只能为byte， short，char， enum，string，int，Character， Integer， Short...

总之x不能为浮点数,我觉得是因为浮点数不能精确存储

y必须与x相匹配，x能自动转换为y

y只能为常量

switch语句的穿透

switch （x） {
	case  y1 :
	case  y2 :
		System.out.println();
}