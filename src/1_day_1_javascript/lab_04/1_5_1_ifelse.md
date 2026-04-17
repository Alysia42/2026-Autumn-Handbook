# 5.1 - If, Else If, Else

> [!INFO] If Statements
> Use the `if` statement to specify a block of JavaScript code to be executed if a condition is true.
> 
> ```js
> if (condition) {
>   //  block of code to be executed if the condition is true
> }
> 
> // make a "Good day" greeting if the hour is less than 18:00:
> hour = 19
> if (hour < 18) {
>   greeting = "Good day";
>   console.log(greeting);
> }
> ```

> [!IMPORTANT] JavaScript is case-sensitive
> Note that `if` is in lowercase letters. Uppercase letters (If or IF) will generate a JavaScript error.

> [!INFO] Else if statements
> 
> Use the `else if` statement to specify a new condition if the first condition is false. Remember that if statements apply **sequentially**, so following conditions will only run if the **previous conditions are false**.
> 
> ```js
> if (condition1) {
>   //  block of code to be executed if condition1 is true
> } else if (condition2) {
>   //  block of code to be executed if the condition1 is false and condition2 is true
> } else {
>   //  block of code to be executed if the condition1 is false and condition2 is false
> }
> 
> // If time is less than 10:00, create a "Good morning" greeting,
> // Otherwise, if the time is less than 20:00, create a "Good day" greeting
> // Otherwise, create a "Good evening" greeting:
> time = 15
> if (time < 10) {
>   greeting = "Good morning";
> } else if (time < 20) {
>   greeting = "Good day";
> } else {
>   greeting = "Good evening";
> }
> ```

> [!INFO] Else Statements
> 
> Use the `else` statement to specify a block of code to be executed if the condition is false.
> 
> ```js
> if (condition) {
>   //  block of code to be executed if the condition is true
> } else {
>   //  block of code to be executed if the condition is false
> }
> 
> // if the hour is less than 18, create a "Good day" greeting
> // otherwise the greeting is "Good evening":
> hour = 10
> if (hour < 18) {
>   greeting = "Good day";
> } else {
>   greeting = "Good evening";
> }
> ```

> [!IMPORTANT] Order
> If, else if and else statements must be in order. You must start with an if statement, else statements must be at the end. Else if statements should go just after if statements.

> [!SUCCESS] Your Turn: Conditionals Task
> Set your favorite color in the variable below then use conditionals to print a message:
> 
> ```js
> let favoriteColor = "red"; // try changing this to blue, green, etc
> ```
> 
> - If the color is **Red** → print `Roses are red`
> - If the color is **Blue** → print `The sky is blue`
> - For any other color → print `That's a cool color!`


