# Customise Your AI

**Right now, the AI is not responding to the text you sent in Discord. Let’s change that by using input from the user.**

---

### Add an Input Option

> [!INFO] Info
> To accept text input, we need to add a string option to the `/ask` slash command.

> [!TIP] Tip
> What method lets you define options in `SlashCommandBuilder`?
>
> ```javascript
> .addStringOption((option) =>
>     option
>         .setName('...')  // What should we call this input?
>         .setDescription('...')  // How will you describe the input?
>         .setRequired(true)
> )
> ```

---

### Read the User Input

> [!INFO] Info
> In the `execute()` function, we can extract what the user typed using `.getString()`.

> [!TIP] Tip
> Use the name you gave your option in the previous step.
>
> ```javascript
> const prompt = interaction.options.getString('...');
> ```

> [!Task] Tasks
> 1. Use the input from Discord as the **prompt** for your AI client.
> 2. Where are you currently hardcoding the prompt? Replace that with the `prompt` variable you just defined.

