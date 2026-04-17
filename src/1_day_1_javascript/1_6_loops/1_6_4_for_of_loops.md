# 6.4 - Could you repeat that v4?

> [!INFO] For...of loops
> The `for…of` loop iterates over the **values** of an **iterable** object (arrays, strings, Maps, Sets, etc.).
> 
> ```js
> let nums = [45, 52, 3, 5, 10, 11];
> 
> for (number of nums) {
>   console.log(number);  // Prints the value
> }
> // Output:
> // 45
> // 52
> // 3
> // 5
> // 10
> // 11
> ```

> [!TIP] Use case
> Use `for…of` when you need direct access to elements.
> If you need the indexes of an array, a traditional for loop or `array.entries()` is a better choice.
> To iterate over object properties, use `for…in` or `Object.keys()` / `Object.entries()`.

> [!QUESTION] Question
> What’s the main difference between `for...in` and `for...of`?
> Which one would you use if you wanted to loop over a string’s characters?

> [!SUCCESS] Tasks
> 1. Create an array of 5 hobbies or interests.
> 2. Use `for...of` to print each one.
> 3. Try the same thing with a string (e.g. "hello") and print each letter.
> 4. Try mixing it up: can you figure out how to get both index and value? (Hint: use .entries() with for...of!)
>  
> Bonus: Compare the output of `for...in` vs `for...of` on the same array!