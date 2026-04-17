# 3 - Data Types

In this part you will learn about:
- Strings
- Numbers
- Booleans
- Extracting the type of variables

On top of strings, numbers and booleans, there are 5 other data types that JavaScript has mentioned in the slides!

> [!TIP] Why do we need data types?
> In programming, data types are an important concept. You can get some strange behaviour in computers when you combine data types, so most languages throw errors if you combine 2 different data types. JavaScript **does not** throw these errors, but that doesn't mean you shouldn't care about mixing data types! Instead of this:
> 
> ```js
> let x = 123 + "chicken";  //bad!!!
> ```
> You should have:
> ```js
> let x = "123" + "chicken"; //good :D
> ```