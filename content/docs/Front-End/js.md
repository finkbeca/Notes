---
title: Javascript
weight: 2
bookToc: true
---

# Javascript


# Typescript
- [Documentation](https://www.typescriptlang.org/docs/handbook/2/classes.html)  
- Same runtime as js code
- Superset of JS
- Types are removed after going through a static check and being compiled.
-  allows you to create objects with inferred types ```name : string ``` 
- If you provide and object that doesn't match the object's interface, Typescript will warn you.  
- Besides boolean, bigint, null, number, string, symbol and undefined, Typescript introduces the type (any) that allows anything, unknown, never, and void.   
-A popular use-case for union types is to describe the set of string or number literals that a value is allowed to be:  

```
type WindowStates = "open" | "closed" |"minimized";
type LockStates = "locked" | "unlocked";
type PositiveOddNumbersUnderTen = 1 | 3 | 5 | 7 | 9
```

- Allows you to specify input parameter types
```// Parameter type annotation
function greet(name: string) {
  console.log("Hello, " + name.toUpperCase() + "!!");
}```
- Allows you to specifcy output parameter types, if not specified it will be inferred.
``` function greet(): string {
    return "Hello"
} 
```