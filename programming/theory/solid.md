# SOLID Principles
20220222204304

#programming

A mnemonic acronym for 5 design principles intended to make software more understandable, manageable, and maintainable

## Summary
- Single responsibility principle
    - do one thing and do it well
- Open/closed principle
    - open for extension, closed for modification
- Liskovs substitution principle
    - where ever you use a base type you should be able to use a subtype and not break
    - contracts must be honored
        - can't accept less than the parent is willing to
        - can't return more than the parent is willing to
        - invariants need to be honored
- Interface segregation principle
    - many specific interfaces is better than fewer general interfaces
- Dependency inversion principle
    - high level modules e.g. `System` should not depend on low level modules `System.Text.Json`
    - both should depend on interfaces
    - abstractions should not depend on details
