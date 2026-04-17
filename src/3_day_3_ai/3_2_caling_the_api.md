# Calling the API

### Define An `async` Function
> [!INFO] Info
> `async` means this function can use `await` inside it.

> [!TIP]  Tip
> ``` Javascript
>   async function nameOfFunction()
> ```

### `try` block
> [!INFO] Info
> - This is where you put code that **might fail** (we will talk about how to handle the fail in the next section), in this case your API Call.

> [!TIP]  Tip 
> ```javascript
>    try {
>        ...
>    }
> ```

### Send A Request to the API
> [!INFO] Info 
> - `fetch(...)` sends a GET request to the URL.
> - `await` means "wait for the response before continuing."
>    

> [!TIP]  Tips
> ```javascript
>        const response = await fetch('<url of your API>');
>    ```

### Parse the JSON Response
> [!INFO] Info
> The API returns something like:
> ```JSON
>    {
>    "data": ["Response from AI"]
>    }
> ```
> - `await response.json()` reads the body of the response and turns it into a JavaScript object.
> - The result is stored in the `data` variable.

> [!TIPS] Tips
> ```Javascript
>    const data = await response.json();
> ```

### Print the Response to the Console
> [!INFO] Info
> - `data.data` is an array of facts.
> - `data.data[0]` gives you the first fact.

> [!TIP]  Tip
> ```javascript
>   console.log(...);
> ```