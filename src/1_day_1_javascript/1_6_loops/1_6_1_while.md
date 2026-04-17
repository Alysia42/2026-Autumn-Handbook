# 6.1 - Could you repeat that v1?

> [!INFO] While loops
> The while loop loops through a block of code as long as a specified condition is true.
> 
> ```js
> while (condition) {
>   // code block to be executed
> }
> 
> // This loop will run, over and over again, as long as the variable i
> //  is less than 10:
> while (i < 10) {
>   text += "The number is " + i;
>   i++;
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
> // This loop counts down the days until winter. It runs as long as 
> // daysUntilWinter is greater than 0:
> let daysUntilWinter = 5;
> while (daysUntilWinter > 0) {
>   console.log("Days until Winter: " + daysUntilWinter);
>   daysUntilWinter--; // Decrease the counter by 1
> }
> console.log("It's Winter!");
> // Output:
> // Days until Winter: 5
> // Days until Winter: 4
> // Days until Winter: 3
> // Days until Winter: 2
> // Days until Winter: 1
> // It's Winter!
> ```

> [!CAUTION] Infinite Loop
> If you forget to update the variable in the loop condition, the loop might never end (infinite loop). It can make your program freeze or hang because it keeps running forever.

> [!SUCCESS] Your Turn: While Loop Task
> Follow these steps to complete the task:
> 1. Create a variable called `start` and set it to any positive number.
> 2. Create a variable called `count` and set it to 0.
> 3. Create a **while** loop that runs while `start` is **greater than 0**.
> 4. Inside the loop:
>    - Subtract 1 from start
>    - Add 1 to count
>    - Print the value of count
> 5. After the loop finishes, print `Loop finished!`

> [!SUCCESS] Your Turn: While Loop Task 2
> 1. Create a variable `steps` and set it to 0.
> 2. Create a variable `n` and set it to any positive number.
> 3. Create a while loop that runs while `n` is not equal to 1.
> 4. Inside the loop:
>    - If n is even, then set `n = n / 2`.
>    - Else, set `n = n * 3 + 1`.
>    - Increase `steps` by 1
> 5. After the loop finishes, print the value of `steps`.
