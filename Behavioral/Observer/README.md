## 观察者模式
观察者模式在对象间定义了一种依赖关系，从而当某个对象的状态改变后，它的所有依赖对象都将得到通知

建立一种对象与对象之间的依赖关系，一个对象发生改变时将自动通知其他对象，其他对象将相应做出反应。在此，发生改变的对象称为观察目标，而被通知的对象称为观察者

观察者模式在观察目标和观察者之间建立一个抽象的耦合。

观察者模式就像关注商品那样, 商品有很多人关注, 当价格发送变动, 会通知每个关注该商品的人, 价格变动了.
MVC模式中M(模型)与V(视图), Model发生变化, View随之变化. 

维基百科:
> 观察者模式是一种软件设计模式，其内的一个对象（称为主题），会维护一组依赖对象（称为观察者），当对象的状态改变后，它通常通过调用依赖对象的某个函数来自动通知它们。

角色:
- 抽象主题(Subject)角色： 将观察者对象的引用保存在一个聚集里，每个主题都可以有任何数量的观察者。抽象主题提供接口，可以增加和删除观察者对象。抽象主题角色又叫做抽象被观察者
(Observable)角色。
- 具体主题(ConcreteSubject)角色： 将有关状态存入具体观察者对象；在具体主题的内部状态改变时，给所有登记过的观察者发出通知。具体主题角色又叫做具体被观察者(Concrete Observable)角色。
- 抽象观察者(Observer)角色： 为所有的具体观察者定义一个更新接口，在得到主题的通知时更新自己。
- 具体观察者(ConcreteObserver)角色： 观察者的具体实现对象，实现抽象观察者角色所要求的更新接口，以便使本身的状态与主题的状态相协调。如果需要，具体观察者角色可以保持一个指向具体主题对象的引用。

缺点:
- 如果一个观察目标对象有很多直接和间接的观察者的话，将所有的观察者都通知到会花费很多时间
