# 4.2 - Assignment Operators

> [!INFO] Assignment Operators
> | **Operator** | **Meaning**                                                        | **Example**         |
> | ------------ | ------------------------------------------------------------------ | ------------------- |
> | =            | Equals: Assigns a value                                            | x = y               |
> | +=           | Plus Equals: Assigns the original value plus the new value         | x += y // x = x + y |
> | -=           | Minus Equals: Assigns the original value minus the new value       | x -= y // x = x - y |
> | \*=          | Multiply Equals: Assigns the original value times the new value    | x *= y // x = x * y |
> | /=           | Divide Equals: Assigns the original value divided by the new value | x /= y // x = x / y |
> | %=           | Modulo Equals: Assigns the original value modulo the new value     | x %= y // x = x % y |
> | ++           | Increases the variable by 1                                        | x++                 |
> | --           | Decreases the variable by 1                                        | x--                 |

> [!TIP] Code Examples
> ```js
> x = 10;
> x += 3; // shorthand for x = x + 3
> console.log(x); // should output 13 since 10 + 3 = 13
> 
> x = 10;
> x /= 5; // shorthand for x = x ÷ 5
> console.log(x); // outputs 2, since 10 ÷ 5 = 2
> 
> x = 10;
> x++; 
> console.log(x); // outputs 11, since 10 + 1 = 11
> ```

> [!SUCCESS] Assignment Operators
> 1. With your existing number variables, apply some assignment operators to them.
> 2. `console.log()` the output of your variables after applying these operators!