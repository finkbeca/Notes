---
title: Rust
weight: 2
bookToc: true
---

- Variables in Rust are immutable to make a variable mutable (ability to change value once defined) use ``` mut ``` such as ```let mut x = 5 ```
- Variable types are ``` u32 ``` unsigned 32 bit integer, ``` s32 ``` signed 32 bit integer, ``` f32 ``` 32 floating floating value, there are many more but these are the basics
- Tuples are defined as ``` let tup1 = (1,2,3)``` to destructure a tuple into independent variables use ``` let (a,b,c) = tup1 ```, in this case a =1 , b=2 , and c =3.
- Code blocks are a method to further limit scope within a function, using curly braces you can further limit the scope of a function or use it for variable shadowing. 
- Shadowing is the process of redeclaring a variable of the same name within a different scope, such as a code block. 
- Structs can be defined in two different methods they can be defined as ```struct <vartype> {num1: u32,num2: u32,} ``` or as  ``` struct <vartype> (u32, u32) ``` , accessing the values the first way can be done using <vartype>.num1 or <vartype>.num2 while the second can be done with indexing such as <vartype>.0 or <vartype>.1  
- Pass by reference in R is similar to that of R, with referencing and dereferencing acting the same, note though that you can not have a variable be mutable as well as a reference to the variable. If the referenced variable is mutable   
***Vectors***  
- Vectors defined ``` let my_vec: Vec<i32> = Vec::new() ``` or ``` let my_vec vec![1,2,4,5] ``` where values are 0-indexed and getting the second element use ```my_vec[1]```  
- Adding new elements to a vector list with ```my_vec.push(6);``` where 6 is the new element added  
- Removing elements based on index such as ``` my_vec.remove(2)``` where the third element 4 is removed.   
- Note adding and removing elements to a vector the vector MUST be mutable, defined with ```mut``` when the variable is defined.   
- Iterate over elements without losing ownership ```for number in my_vec.iter() { //do stuff inside the loop } ```  
***Reading a File***
- Import with  ```use std::fs::File ``` and use ``` std::io::prelude::*; ```    
- Read in the file to a variable such as ``` let mut file = File:::open("info.txt").expect("Can't Open FIles");```
- Can use file.read_to_string(<string_name>) to read in string from a file variable to a mutable string. 
*** CommandLine Arguments*** 
- use std::env
- Let args: Vec<String> = env::args().collect(), the arguments will then be a list of strings, note that the first index is automatically defined. *** Trait Example ***
``` struct Person{ name: String, age: u8 }

    trait hasEducation {
        fn education(&self);

        fn has_education(&self) -> bool;
    }

    impl HasEducation for Person {

        fn education(&self) { 
            println!("Has education!);
        }

        fn has_education(&self) -> bool {
            return (self.age > 5)
        }
    }
```
