## 工厂方法模式
维基百科说
> 在基于类的编程中，工厂方法模式是一种创建模式，它使用工厂方法来处理创建对象的问题，而无需指定将要创建的对象的确切类。
这是通过调用工厂方法来创建对象来完成的 - 在接口中指定并由子类实现，或者在基类中实现并可选地由派生类覆盖 - 而不是通过调用构造函数。

简单工厂模式加强版,实现了S.O.L.I.D原则中「D」的依赖倒置.

依赖倒置原则
 1. 高层次的模块不应该依赖于低层次的模块，两者都应该依赖于抽象接口。
 2. 抽象接口不应该依赖于具体实现。而具体实现则应该依赖于抽象接口。

不是由一个工厂类去实例化所有基于父类的子类对象, 每个子类都有自己工厂类
去创建对象. 由工厂子类去决定哪一个类去实例. 每新增一个新的子类, 都需要创建对应的工厂子类.
假如用简单工厂模式, 都需要去修改工厂类, 违反开闭原则(对扩展时开放, 对修改时封闭). 

与简单工厂模式不同的是, 简单工厂模式的工厂类只有一个静态创建对象方法, 无法形成基于继承等级模式
工厂方法克服了简单工厂无法形成基于继承等级模式, 又保持了封装对象创建的过程优点. 
对于客户端来说, 只需记住创建工厂子类的名称, 无需知道创建对象的如何实现的.
```php
// 客户端
use Patterns\Creational\FactoryMethod\CircleButtonFactory;
$factory = new CircleButtonFactory();
$circleButton = $factory->createButton();
echo $circleButton->draw();
```

工厂方法模式适用环境:
- 一个类不知道它所需要的对象的类

工厂方法模式缺点:
 - 添加新产品时，除了增加新产品类外，还要提供与之对应的具体工厂类，系统类的个数将成对增加
 - 虽然保证了工厂方法内的对修改关闭, 但对于客户端更换另一种产品来说则需要修改客户端代码.
 - 客户端需记住创建子类的工厂子类名称