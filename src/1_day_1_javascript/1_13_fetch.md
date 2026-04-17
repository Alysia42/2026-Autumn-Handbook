# 8.4 - Fetch

> [!INFO] Fetch calls
> `fetch` is the function we use to make an API call in Javascript.
> 
> In its most simple form, we simply call fetch using `await` (and then `await` again on some of the contents, as the thing returned by `fetch` is quite complex and we only need a little bit of it):
> ```js
> let response = await fetch("https://meowfacts.herokuapp.com");
> let data = await response.json();
> console.log(data);
> ```
> `.json()` converts the response from `fetch` into data we can use.

> [!INFO] Query parameters
> 
> To add query parameters, we need to manually add them to the URL. (See the Query Parameters page for how to do this!).
> 
> ```js
> let response = await fetch("https://meowfacts.herokuapp.com/?count=3")
> let data = await response.json()
> console.log(data)
> ```

> [!SUCCESS] Try it yourself:
> 
> - Pick an API from the list in the API page, or use our meow facts API: `https://meowfacts.herokuapp.com/` (you can find documentation [here](https://github.com/wh-iterabb-it/meowfacts)), and create a program that prints out different cat facts. 
> 
> - Use a loop to call an API multiple times, with different paramaters each time.
> - Try combining two APIs at once, or more! How might this be useful to build a larger application?
> - Further combine APIs and the other features you've been taught to your hearts content!
> 

> [!INFO] Automagical query parameters
> 
> There is a method of automatically adding query parameters, but it's out of scope for this course. We provide it here anyway - perhaps you could try and figure out how it works? If not, you can use it as much as you like anyway.
> 
> ```js
> let params = new URLSearchParams();
> params.append("count", 3)
> 
> let response = await fetch(`https://meowfacts.herokuapp.com/?${params}`)
> let data = await response.json()
> console.log(data)
> ```
> 
> Note the backticks \` instead of quotes ", and the question mark!
