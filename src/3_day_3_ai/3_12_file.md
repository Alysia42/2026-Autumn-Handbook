# Creating files

Generally, GPT bots have no memory (context), built in. They essentially forget everything you tell it the second that it is finished with your request. 

Thus, in this section, we will teach you how to give it a little bit of context by writing each message to a file

> [!INFO] Creating a file
> To write to a file, use the `fs` module. The `fs` module provides us with a bunch of functions that allow us to read and write to files, similar to the `file()` function in python. 
> Example: 
> ``` javascript
> import fs from "fs"; 
>
> const file = fs.createWriteStream("filename.txt", { flags: 'a' }); 
> ```
> By setting the `'a'` flag in the `createWriteStream`, this tells the computer that we want to "append" to the file instead of overwriting it. 
> This is particularly helpful when we want to continiously write our messages to the log.

> [!SUCCESS] TASKS
> - When your bot starts, create a `writeStream` called  `messages.txt` 


