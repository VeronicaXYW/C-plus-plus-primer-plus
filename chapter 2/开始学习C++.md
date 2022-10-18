int main(void)。void表示该函数不接受任何参数，在C++可以省略，即默认是void。所以在各种子函数中，比如int add(int a, int b)，必须在括号中写明自己接受什么参数。

每个cout的输出都从前一个输出的末尾开始。

只有分号可以分割语句，换行是没用的。但是不要把一个整体分开，比如main, int。

为什么使用变量之前必须要声明？方便。没声明过的变量，程序会报错。如果不需要声明就能用，打错字也能误创造一个新变量，这种bug在大量代码中会很难发现。有些编译器甚至可以自动提示已经声明过的变量。

类定义描述的是数据格式及其用法，对象则是根据这一套规范创造的实体。比如演员是进行表演的一类人，某个著名演员是演员这个类中的一个对象。演员这个类里面的人可以执行什么操作，那么这个演员也可以执行这样的操作。

函数
函数需要以下几个要素：需要一个原型。函数头和函数体；是否要接受参数？如果不需要接受参数，在小括号里写明void；是否返回值？如果不返回值，函数类型处写明void。
以下是详细内容：

使用函数之前，要知道被调用函数（called function）的参数类型和返回值类型。函数还需要原型。
double sqrt(double);
递一个double说明该函数会返回一个double类型的数据，小括号里的double表示该函数需要一个double类型的数据。
分号显示该行是一条语句，缺少这个括号，编译器就会以为这是个函数头，函数头后面必须接具体的函数内容。

函数可以不传数据回去，开头用void，不妨碍它可以发挥别的作用。如以下函数所示：
```
#include<iostream>
void simon(int);//在小括号里用int n也可以

int mian()
{
	using namespace std;
	simon(3);
	cout << "pick an integer: ";
	int count;
	cin >> count;
	simon(count);
	cout << "done!" << endl;
	return 0;
}

void simon(int)
{
	using namespace std;
	cout << "simon says touch your toes " << n << "times" << endl;
}//void function doesn't need to return statement.

```
因为simon()函数没有返回值，所以不能用simple = simon(3); 这种语句

解释return 0;
main()函数的return 0;是把0返回给了谁？可以看作返回给了系统，部分系统是运行程序并测试它们的返回值，如果最后可以返回0，则视为程序运行成功。

可以通过这几种方式来调用函数，如下例：
```
int stonetolb (int sts)
{
	return 14 * sts;
}

int stonetolb(int sts)
{
	int pounds = 14 * sts;
	return pounds;
}

int aunt = stonetolb(20);

int aunts = aunt + stonetolb(10);

cout << "Ferdie weighs " << stonetolb(16) << " pounds." << endl;
```

命名空间
什么是命名空间？引用命名空间，才可以使用其中已经约定好的规则。
有四种引用方法，如下所示：
1. 全局引用。在所有的函数体之前声明using namespace std;
2. 局部引用。在需要用到的函数体里声明using namespace std;
3. 局部，且用到哪个声明哪个。在需要用到的函数体里声明using std::cout;
4. 用的时候再引用。在cout、cin、endl之前加上前缀std::

已看完第二章，习题都会做，编程部分都对。
