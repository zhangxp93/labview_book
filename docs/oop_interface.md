# 接口

## “类”的种类

LabVIEW为了降低学习门槛，在2020之前，只提供了一种“类”。但是如果我们看一下其它面向对象的编程语言，会发现，它们通常可以实现很多种不同类型的“类”，而且有很多不同的分类方法。

访问权限
按照访问权限来分，类的属性（数据）和方法（函数或VI）可以分为：

* 公有：类内和类外都可访问。类内访问是指在同一个类的方法（函数或VI）的代码中可以读写，否则就是类外访问。
* 私有：类内可访问，类外不可访问。
* 保护：可以在类内，或者子类内访问。
* 友元：有的编程语言支持友元的概念，是指某个类的属性和方法可以被其它一些指定为友元的方法或类访问到。

在LabVIEW中，类的属性（数据）只有一种访问权限，私有。数据只能被类内的VI读写。而所有的方法（VI）却都是共有的，可以在任何其它VI中被调用。

是否需要实例化

* 静态：静态的属性和方法不需要类实例化就可以被访问。
* 动态：动态的属性和方法只能通过类的某个实例进行访问。

需要格外注意的是，LabVIEW中的“基于动态分配模板”和“基于静态分配模板”与讨论其它语言时候所说的动态静态完全是不同的概念。
访问权限来分，类的属性（数据）和方法（函数或VI）可以分为：




再来看一下，方法可以分为哪几种。
* 普通类函数：大多数语言里，普通的函数对应LabVIEW类中的“静态分配”VI。这种函数或VI不会被子类中的函数或VI覆盖。
* 虚函数：对应LabVIEW类中的“动态分配”VI。这种函数或VI会被子类中的函数或VI覆盖。
* 抽象函数：LabVIEW中没有这个概念。抽象函数是一个虚函数，但是它只定义了函数的名字和输入输出参数类型，并没有实现（编写代码给）这个函数。抽象函数需要在子类中实现。

