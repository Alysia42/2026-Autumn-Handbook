# Handling the Error

> [!INFO] Info
> - If `fetch` fails (e.g. no internet, server down), the code will jump to `catch` and print the error message.
> - You'll want see a helpful message like:
> ```
>   Something went wrong: TypeError: Failed to fetch
> ```

>[!TIP]
> ```javascript
> console.error('Something went wrong:', error);
> ```
