# Reading from a file

In this section, you will learn to read from files in JavaScript.

> [!INFO] Writing to a file
> To read from a file, we cannot simply use the `createWriteStream` we created earlier, but we have access to this function called `readFileSync()` that reads in the entire file.
> Example: 
> ``` javascript
> const data = fs.readFileSync('./messages.txt', { encoding: 'utf8', flag: 'r' });
>
> console.log(data);
> ```
> the `Sync` of `readFileSync` at the end of the function name means that the function is synchronous. This means that the code will wait until the function is done until it moves on with the rest of the code. 

> [!QUESTION] Question
> Now, we should read the user messages before we send our request to our AI API. How might we do so? 
> <br><br>
> **Perhaps we should read the messages into a variable `messsages` in our event handler before we send the request.**

> [!SUCCESS] TASKS
> - Everytime that a message is sent to the AI, attach a list of all the messages that the user has sent previously. 
> - Test that your AI can correctly remember things. For example, if you tell it your name, can it still remember ~2 requests afterwards?


