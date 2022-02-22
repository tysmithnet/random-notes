# Copy Elision
20220222033417

#cpp

A **compiler optimization** that eliminates unnecessary copying of objects

## Summary
- elision means 
    - "an omission of a passage in a book, speech, or film"
    - "the process of joining together or merging things, especially abstract ideas"
- cpp standard allows compilers to make optimization if the observed behavior is the same as if it were implemented in the non optimized way
    - sometimes called the **as if rule**
- **return value optimization** is the most obvious example
    - don't copy the temporary value from the function into the result object, just write directly to the return object