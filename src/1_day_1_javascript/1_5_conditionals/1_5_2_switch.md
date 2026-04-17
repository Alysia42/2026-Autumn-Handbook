# 5.2 - Switching it up!
> [!IMPORTANT] This Exercise Is Optional

> [!INFO] Switch Statements
> A `switch` statement allows you to execute different blocks of code based on the value of a variable. It’s an **alternative** to using multiple if else statements when you’re checking one variable against several possible values.
> 
> How it works:
> 
> 1. The switch expression is evaluated once
> 2. The value of the expression of compared with the values of each case
> 3. If there is a match, the associated code black is executed
> 4. If there is no match, the default code block is executed
> ```js
> switch (expression) {
>   case x: // If expression === x
>     // code block
>     break;
>   case y: // Else if expression === y
>     // code block
>     break;
>   default: // Else
>     // code block
> }
> ```

> [!TIP] Code Example
> ```js
> let weather = "Sunny";
> 
> if (weather === "Windy") {
>   console.log("Wear a jacket!");
> } else if (weather === "Rainy") {
>   console.log("Bring an umbrella!");
> } else if (weather === "Sunny") {
>   console.log("Put sunscreen on!"); 
> } else {
>   console.log("Unknown weather");  
> }
> ```
> Is equivalent to:
> ```js
> // check the value of the weather variable and execute different code 
> // based on which weather it is
> let weather = "Sunny";
> 
> switch (weather) {
>   case "Windy":
>     console.log("Wear a jacket!");
>     break;
>   case "Rainy":
>     console.log("Bring an umbrella!");
>     break;
>   case "Sunny":
>     console.log("Put sunscreen on!");
>     break;
>   default:
>     console.log("Unknown weather");
> }
> ```

> [!CAUTION] Break Statement
> When JavaScript reaches a break keyword, it breaks out of the switch block.
> If you omit the break statement, execution will continue to the next case regardless of whether its condition matches.

> [!INFO] Default Case
> The default keyword specifies the code to run if there is no case match. It is not necessary to break the last case in a switch block since the block breaks ends there anyway.

> [!SUCCESS] Your Turn: Switch Task
> Rewrite this if...else if chain using a switch statement
> 
> ```js
> potion = "healing"; // try changing this to other values
> if (potion === "healing") {
>   console.log("Restores health!");
> } else if (potion === "invisibility") {
>   console.log("You disappear!");
> } else if (potion === "strength") {
>   console.log("You feel powerful!");
> } else if (potion === "poison") {
>   console.log("Ouch! Toxic!");
> } else {
>   console.log("Unknown potion!");
> }
> ```
