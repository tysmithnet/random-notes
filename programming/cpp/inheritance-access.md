# Inheritance Access
20220222210035

#cpp #oop #inheritance

Public, protected, and private can be used on members but also on the inheritance itself to change what is visible to the derived type

## Summary
- whatever the level of inheritance, nothing inherited can be less restrictive than what is given as the access modifier
    - if private, then anything inherited is private
- useful if you want to control what is exposed as the derived types api
Motivating example:
```cpp
class A 
{
    public:
       int x;
    protected:
       int y;
    private:
       int z;
};

class B : public A
{
    // x is public
    // y is protected
    // z is not accessible from B
};

class C : protected A
{
    // x is protected
    // y is protected
    // z is not accessible from C
};

class D : private A    // 'private' is default for classes
{
    // x is private
    // y is private
    // z is not accessible from D
};
```
- public is what we think of from C#
- protected means that anything public in the base class is now protected in the derived class
    - not very common
- private means everything is private