# Release Note

## 0.5.2
- 支持使用`PrivateAccessor`访问父类中的私有成员 (issue-91)
- 修复在较高版本JVM下的非法类型错误 (issue-112)
- 修复Mock目标为接口类型时的字节码异常 (issue-82)

## 0.5.1
- 在`VERBOSE`级别诊断日志中使用更易于阅读的方法签名格式
- 增加对JUnit5参数化测试的支持 (issue-98)
- 修复在调用参数中包含三元表达式时的Mock异常（issue-92）
- 修复使用`@MockWith`时，日志输出丢失的BUG (issue-99)

## 0.5.0
- 分离测试类与Mock类，实现Mock类和Mock方法的复用机制
- 支持测试类与被测类在不同包路径的情况下实施Mock
- 支持将Mock方法生效范围缩小为所属测试类的测试用例
- 使用`TransmittableThreadLocal`替换基于线程堆栈的Mock上下文识别机制
- 增加专用于输出诊断信息的`@MockDiagnose`注解

## 0.4.12
- 支持`VERBOSE`级别的Mocking过程日志，增强错误自助排查能力
- 支持使用`verifyTargetOnCompile`参数禁用编译期私有目标校验功能
- 支持通过agent参数指定Mock目标的扫描包范围
- 修复一处`ArrayIndexOutOfBoundsException`异常 (issue-52）

## 0.4.11
- 支持测试类访问与自身包路径不同的被测类的私有成员
- 增加`PrivateAccessor`访问的私有方法参数数目检查，提高抗代码重构能力
- 修复被Mock方法包含数组参数可能导致出错的BUG (issue-48)
- 修复一处会导致在IntelliJ中构建找不到私有成员的问题

## 0.4.10
- 修复在Lambda函数中使用Mock出错的BUG（issue-44）
- 修复调用私有方法时参数值不能为null的问题（issue-27）

## 0.4.9
- 修复发起调用的对象不是局部或成员变量时Mock出错的BUG (issue-40)
- 增加`PrivateAccessor`访问目标有效性检查，提高抗代码重构能力 (issue-21)

## 0.4.8
- 修复赋值语句中的私有方法调用无法访问的BUG (issue-33)
- 支持在包含`SpringRunner`的测试中使用Mock (issue-30)
- `@MockMethod`注解支持`targetClass`参数 (issue-24)

## 0.4.7
- 修复由于`MOCK_CONTEXT`引入的堆栈大小错误
- 修复Windows下的`Gradle`构建路径错误 (issue-25)

## 0.4.6
- 修复一处`IINC`字节码处理异常
- 支持使用`TestableTool.MOCK_CONTEXT`变量为Mock方法注入额外上下文参数 (issue-17)
- 不再推荐使用`TestableTool.TEST_CASE`变量来区分测试用例

## 0.4.5
- 修复IntelliJ 2020.3+环境下的私有成员访问编译期错误
- 修复潜在的跨用例初始化空指针异常 (issue-20)
- 支持将运行期修改后的字节码Dump到本地文件

## 0.4.4
- 修复无法访问参数类型包含接口的私有方法的BUG (issue-15)
- 修复Mock无参数的静态方法会出错的BUG (issue-16)

## 0.4.3
- 完善了对私有静态成员的直接访问能力

## 0.4.2
- 支持通过Maven插件设置`TestableAgent`的全局日志级别
- 修复测试类可能被重复注入多余字节码的BUG
- 修复一处导致跨行的方法调用Mock报错的BUG

## 0.4.1
- `@TestableMock`注解已弃用，推荐使用`@MockMethod`和`@MockConstructor`注解

## 0.4.0
- 修复由于默认类加载器变化导致JVM 9+运行时Mock出错的BUG
- 修复多个测试类包含同名Mock方法时潜在的串号问题
- 重构项目结构，增加用于简化依赖配置的`testable-all`模块
- `TestableTool`中与用户无关的内容迁移到了`TestableConst`类型

## 0.3.2
- 支持在Gradle项目中使用私有成员访问和快速Mock功能
- 支持通过`PrivateAccessor`工具类访问私有静态成员

## 0.3.1
- 支持使用`@MockWith`注解打印详细Mock执行过程

## v0.3.0
- 增加`without()`校验器用于匹配指定Mock方法从未被调用的场景
- 支持对Mock调用参数验证时使用模糊匹配

## v0.2.2
- 支持对Mock调用参数进行校验
- 修复JVM 9+的兼容性问题

## v0.2.1
- 支持Mock静态方法
- 支持Mock Kotlin Companion对象的方法
- 支持Mock接口或父类引用指向子类实例时的调用

## v0.2.0
- 支持通过`TestableTool`工具类识别当前的调用上下文
- 增加`testable-maven-plugin`模块用于简化运行时JavaAgent配置
- 不再需要使用`@EnableTestable`注释显式标记测试类
- 重名了现有的各种注解，以便与更好的与实际功能对应

## v0.1.0
- move generated agent jar to class folder
- support mock method of any object

## v0.0.5
- use dynamically runtime modification to replace static `e.java` file
- get rid of unit test framework dependence
- add testable ref field in test class at runtime instead of compile time

## v0.0.4
- use runtime byte code rewrite to invoke testable setup method
- add `TestableUtil` class to fetch current test case and invocation source

## v0.0.3
- use global method invoke to access private members instead of modification in place
- use `e.java` replace `testable` class make code more readable
- introduce `agent` module, use runtime byte code modification to support new operation and member method mocking

## v0.0.2
- add support of member method mocking by compile time code modification

## v0.0.1
- PoC version
- use compile time code modification to support new operation mocking and private field & method access
