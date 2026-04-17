# 8.3 - Async

> [!INFO] Async/Await
> - `async` is shorthand for "Asynchronous"
> - `await` is shorthard for... "Await"
> 
> We use `async` and `await` for computations that may take a long time. In short, using these warns Javascript & the programmer that these operations may be "waiting" for a while, so we are explicitly waiting with `await`.
> 
> In our case, the operations may be slow because using internet APIs can be slow.

> [!INFO] Promises
> 
> All `async` functions, and functions like `fetch`, return a `Promise` instead of a value. A `Promise` is a guarantee that if you `await` the promise, you will get the data inside.
> 
> ```js
> async function one() {
>     return 1;
> }
> ```
> If we did:
> ```js
> let data = one();
> ```
> `data` will be a `Promise`, instead of the data we actually want.
> If instead we do:
> ```js
> let data = await one();
> ```
> Now `data` will be `1`.

> [!INFO] Calling `await`
> 
> If we define our own functions, we must use `async` at the start of the function. Otherwise, you cannot use `await` within the function body, as you have not warned Javascript the operation may take a long time. The following will **not** work:
> ```js
> // Doesn't work!
> function googler() {
>     return await fetch("https://google.com")
> }
> ```
> But this does, because we've added `async`:
> ```js
> async function googler() {
>     return await fetch("https://google.com")
> }
> ```

> [!SUCCESS] Try it yourself
> 
> - Try writing some of the functions we explored earlier with `async`. 
> - Explore how this may require you to change other functions in order to accommodate this new `async` usage. 
> - Do you think this could have consequences in a large code base?
