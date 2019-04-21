## 门面模式
门面模式, 也叫外观模式, 为复杂子系统提供一个简化接口。
维基百科:
> 外观就是一个对象，它为更大规模的代码，如类库等提供简化的接口。

外部与一个子系统的通信必须通过一个统一的外观对象进行，为子系统中的一组接口提供一个一致的界面，外观模式定义了一个高层接口，
这个接口使得这一子系统更加容易使用.

适用环境:
- 客户程序与多个子系统之间存在很大的依赖性
- 当要为一个复杂子系统提供一个简单接口时可以使用外观模式

缺点:
- 不能很好地限制客户使用子系统类
- 若没有一个抽象外观类, 新增新子系统则需要修改外观类