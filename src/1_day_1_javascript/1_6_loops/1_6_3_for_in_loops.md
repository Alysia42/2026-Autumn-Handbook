# 6.3 - Could you repeat that v3?

> [!INFO] For...in loops
> The `for…in` loop iterates over the **properties (keys/indexes)** of an object.  
> When used on arrays, it returns the **indexes** (not the values directly).
> 
> ```js
> let nums = [45, 52, 3, 5, 10, 11];
> 
> for (index in nums) {
>   console.log(index);        // Prints the index
>   console.log(nums[index]);  // Prints the value
> }
> // Output:
> // 0
> // 45
> // 1
> // 52
> // 2
> // 3
> // 3
> // 5
> // 4
> // 10
> // 5
> // 11
> ```

> [!TIP] Use case
> `for…in` is typically used for objects. When looping through arrays, it's better to use `for…of` or a traditional for loop to avoid unexpected behavior.

> [!INFO] For...in loops with objects
> ```js
> let person = { name: "Jamie", age: 22, student: true };
> for (key in person) {
>   console.log(key);          // Prints the property name
>   console.log(person[key]);  // Prints the value of that property
> }
> // Output:
> // name
> // Jamie
> // age
> // 22
> // student
> // true
> ```

> [!QUESTION] Question
> 1. What’s the difference between what `for...in` gives you when looping through an array vs an object?
> 2. Can you explain why using `nums[index]` is needed when looping through arrays?

> [!SUCCESS] Tasks
> 1. Create an object called book with at least 3 properties (e.g., title, author, pages)
> 2. Use a `for...in` loop to print each key and its value
> 3. Then create an array of your top 3 favourite foods
> 4. Use a `for...in` loop to print both the index and the food at that index
> 
> Bonus: Try using `for...of` on the array and compare what it prints!