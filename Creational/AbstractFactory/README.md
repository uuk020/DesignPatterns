## 抽象工厂模式

> 抽象工厂模式,提供一个创建一系列相关或相互依赖的对象的接口, 而无需指定它们的具体的类

维基百科是这样定义的:
>  抽象工厂模式的实质是“提供接口，创建一系列相关或独立的对象，而不指定这些对象的具体类。”

抽象工厂模式, 其实是工厂方法模式再抽象的版本, 工厂方法只能创建一个产品的, 而抽象工厂则是把工厂
类再抽象成为更高级的工厂, 它(工厂类)里面应该包含所有产品的创建的抽象方法. 而不会指定创建对象的具体类, 
而有工厂子类去定义. 理解抽象工厂模式, 需要了解"产品等级结构" 和 "产品族"概念.

- 产品等级结构: 产品等级结构即产品的继承结构，如一个抽象类是电视机，
  其子类有海尔电视机、海信电视机、TCL电视机，
  则抽象电视机与具体品牌的电视机之间构成了一个产品等级结构，
  抽象电视机是父类，而具体品牌的电视机是其子类。

- 产品族: 在抽象工厂模式中，产品族是指由同一个工厂生产的，
  位于不同产品等级结构中的一组产品，
  如海尔电器工厂生产的海尔电视机、海尔电冰箱，海尔电视机位于电视机产品等级结构中，
  海尔电冰箱位于电冰箱产品等级结构中。
  
 因此工厂方法与抽象工厂最大区别厂方法模式针对的是一个产品等级结构，
 而抽象工厂模式则需要面对多个产品等级结构
 之前工厂方法模式例子是用圆形按钮和矩形按钮来实现的, 但抽象工厂模式比工厂方法更抽象的,.
 
 用矩形和圆形按钮来实现有点不恰当, 有两种产品接口 Button 和 Border ，每一种产品都支持多种系列，
 比如 Mac 系列和 Windows 系列。这样每个系列的产品分别是 MacButton, WinButton, MacBorder, WinBorder 。
 为了可以在运行时刻创建一个系列的产品族，我们可以为每个系列的产品族创建一个工厂 MacFactory 和 WinFactory 。
 
适用环境:
- 一个系统不应当依赖于产品类实例如何被创建、组合和表达的细节，这对于所有类型的工厂模式都是重要的。
- 属于同一个产品族的产品将在一起使用，这一约束必须在系统的设计中体现出来。

缺点:
- 假如新增产品类, 则修改抽象工厂, 违反开闭原则.
   