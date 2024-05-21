---
title: C++学习笔记
published: 2024-05-16
description: "C++ learning notes."
image: ""
tags: ["note", "C++"]
category: Study
draft: false
---

## C++

### 1.1 多态
同一个函数在不同的上下文中的多种形态。C++氛围编译时多态（静态）和运行时多态（动态）。

```c++
class A
{
public:
    void func1() {};
    void func2() {}; // 输出sizeof(a)为1
    virtual void vfunc() {}; // 输出sizeof(a)为8或4
};
A a;
```
1. 编译时多态（静态多态）
通过函数重载和运算符重载实现。编译时多态在编译期间确定
```c++
class Example {
public:
    void show(int x) {
        cout << "Integer: " << x << endl;
    }
    void show(double x) {
        cout << "Double: " << x << endl;
    }
};
```
2. 运行时多态（动态多态）
通过虚函数和继承实现
```c++
class Base {
public:
    virtual void show() {
        cout << "Base class show function" << endl;
    }
    virtual ~Base() {}
};

class Derived : public Base {
public:
    void show() override {
        cout << "Derived class show function" << endl;
    }
};

int main() {
    Base* b;
    Derived d;
    b = &d;
    b->show(); // 输出：Derived class show function
    return 0;
}
```
继承和多态是紧密相关的。继承提供了创建层次结构和代码复用的机制，而多态允许基类指针或引用调用派生类的重写方法，实现动态绑定。

3. 虚函数和多态：
* 虚函数： 基类中的函数声明为virtual，派生类可以重写该函数。通过基类指针或引用调用虚函数时，会根据实际对象类型调用对应的函数。
* 纯虚函数和抽象类： 纯虚函数用`= 0`表示，包含纯虚函数的类称为抽象类，不能实例化。派生类必须实现纯虚函数。

### 面试问题：
1. 什么是重载和模版
2. 