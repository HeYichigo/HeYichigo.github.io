---
permalink: /java/object.html
---
``` java
import java.lang.Object
```

```java
/**
* @start:  2021/01/20
* @update: 2021/01/20
* @auther: Yichigo
*/
```

## 关于 Object 的个人理解

众所周知，`Object`是所有类的基类，它规定了一个类的基本行为。

在Java中，你可以在自己的类中`@Override`这些行为来定义自己的实现。

> 复习一下`@Override`的规则吧 [<sup>1</sup>](#refer-anchor)
>
> - 参数列表与被重写方法的参数列表必须完全相同。
> - 返回类型与被重写方法的返回类型可以不相同，但是必须是父类返回值的派生类（java5 及更早版本返回类型要一样，java7 及更高版本可以不同）。
> - 访问权限不能比父类中被重写的方法的访问权限更低。例如：如果父类的一个方法被声明为 public，那么在子类中重写该方法就不能声明为 protected。
> - 父类的成员方法只能被它的子类重写。
> - 声明为 final 的方法不能被重写。
> - 声明为 static 的方法不能被重写，但是能够被再次声明。
> - 子类和父类在同一个包中，那么子类可以重写父类所有方法，除了声明为 private 和 final 的方法。
> - 子类和父类不在同一个包中，那么子类只能够重写父类的声明为 public 和 protected 的非 final 方法。
> - 重写的方法能够抛出任何非强制异常，无论被重写的方法是否抛出异常。但是，重写的方法不能抛出新的强制性异常，或者比被重写方法声明的更广泛的强制性异常，反之则可以。
> - 构造方法不能被重写。
> - 如果不能继承一个类，则不能重写该类的方法。

## Object 定义的行为

```java
public final native Class<?> getClass();
```

该方法返回的是：该对象的运行时类。  

> 对于运行时类的理解：
>
> 一个类（比如：`People`）在创建时， *Java Virtual Machine* 会创建一个`Class`类型的对象 (`Class<People> peopleClass`)  
>
> 这个对象保存了该类在正在运行的 *Java Virtual Machine* 中所有信息

```java
public native int hashCode();
```



## 引用

<div id="refer-anchor"></div>

[1] [菜鸟教程：Java重写(Override)与重载(Overload)](https://www.runoob.com/java/java-override-overload.html)
