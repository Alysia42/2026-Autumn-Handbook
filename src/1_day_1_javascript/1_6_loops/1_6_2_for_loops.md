# 6.2 - Could you repeat that v2?

> [!INFO] For Loops
> A `for` loop repeats a block of code a known number of times. It’s commonly used when the number of iterations is known ahead of time.
> 
> ```js
> for (initialization; condition; final-expression) {
>   // code block to be executed
> }
> 
> // This loop prints numbers from 0 to 9:
> for (let i = 0; i < 10; i++) {
>   console.log("The number is " + i);
> }
> // Output:
> // The number is 0
> // The number is 1
> // The number is 2
> // The number is 3
> // The number is 4
> // The number is 5
> // The number is 6
> // The number is 7
> // The number is 8
> // The number is 9
> 
> // This loop prints even numbers up to 10:
> for (let i = 0; i <= 10; i += 2) {
>   console.log(i);
> }
> // Output:
> // 0
> // 2
> // 4
> // 6
> // 8
> // 10
> ```

> [!QUESTION] Question
> In a for loop, what are the three parts inside the parentheses used for?
> Can you explain what i++ or i += 2 means in simple words?

> [!SUCCESS] Tasks
> 1. Create a for loop that counts from 1 to 5 and prints each number
> 2. Create another loop that prints out only odd numbers from 1 to 9
> 3. Try changing the start or stop number, does the loop still work?
> 4. Print a fun message with each number, like: "Counting... 1", "Counting... 2", etc.