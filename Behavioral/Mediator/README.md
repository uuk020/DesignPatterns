## 中介者模式
中介者模式引入了一个第三方对象（叫中介者 mediator) 来控制两个对象（叫同事 colleagues) 间的交互。它有助于减少彼此通信的类间的耦合性。
因为现在它们无需了解对方的实现细节。 生活处处充斥中介者, 房屋中介, 出国留学的中介, 还有找工作, 招聘网站也是中介者. 最大中介者就是联合国组织.

对象与对象之间存在很强的, 复杂的关联关系, 彼此对象交互复杂, 互相连接过多, 导致类的可复用性降低, 则需要第三方类来调和, 减少耦合. 因此中介者也叫调停者.

> 在软件工程中，中介者模式定义了一个对象，它对一组对象如何交互进行了封装。这种模式被认为是一种行为型模式，因为它能改变程序运行时的行为。

角色:
- Mediator（抽象中介者）： 定义了同事对象到中介者对象之间的接口
- ConcreteMediator（具体中介者）： 实现抽象中介者的方法，它需要知道所有的具体同事类，同时需要从具体的同事类那里接收信息，并且向具体的同事类发送信息。
- Colleague（抽象同事类）： 它定义各个同事类公有的方法，并声明了一些抽象方法来供子类实现，同时维持了一个对抽象中介者类的引用，其子类可以通过该引用来与中介者通信。
- ConcreteColleague（具体同事类）： 抽象同事类的子类；每个同事对象在与其他同事对象通信时，先与中介者通信，通过中介者来间接完成与其他同事类的通信；在具体同事类中实现了在抽象同事类中声明的抽象方法。

缺点:
- 具体中介者会变复杂, 难以维护
