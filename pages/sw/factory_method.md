---
title: Factory Method 
keywords: oop desgin patterns factory method
sidebar: sw_sidebar
toc: true
permalink: factory_method.html
folder: designer_partners
---


## C++

```cpp

class Foo {

public:

    Foo(args);
    ~Foo();
};

class FooFactory{

public:

    static Foo* createFoo(){

        return new Foo(args);
    }
};

```