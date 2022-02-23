# Polymorphism
20220222211115

#cpp #oop #inheritance #polymorphism

The ability for a **derived** type to **augment or replace the implementation** for an inherited member function

## Summary
- arguable the most important aspect of oop
- requires base methods to be `virtual`
- base methods can be pure aka abstract
    - all pure implies interface type
    - mixed bag implies abstract class

## VTables
- how polymorphism is implemented
- compiler adds a pointer to the class that points to a VTable for the type
- VTable is compiler dependent but could be implemented as an array of function pointers
    - when a child type doesn't override the parent implementation it gets a pointer to the parent's implementation
    - when a child does override it gets a pointer to the classes implementation