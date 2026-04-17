# Writing to files

In this section, you will learn to write to files in JavaScript.

> [!INFO] Writing to a file
> To write to a file, use the `fs` module. The `fs` module provides us with a bunch of functions that allow us to read and write to files, similar to the `file()` function in python. 
> Example: 
> ``` javascript
> const message = interaction.message;
> file.write(message); 
> ```
> Where `file` is a `createWriteStream` that was created earlier.

> [!QUESTION] Question
> We can now write to files, but what event should cause us to do so? What event should happen that would cause us to write our message to a file?
> <br><br> **Potentially this could be an event that triggers every time a message is sent...**

> [!SUCCESS] TASKS
> - Everytime that a message is sent, call the `file.write()` function to write it to a file.
> - Verify that all your messages that are sent are inside the file.


