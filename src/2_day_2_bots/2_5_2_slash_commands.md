# Slash Commands

> [!INFO] Slash commands
> A slash command only appears when starting a message with `/`. 
>
> Instead of having the bot automatically respond to events, slash commands only run when someone uses the slash command.

> [!TIP] Creating our Commands Folder
> Each slash command should be put in its own file, in the folder `utility` (found inside `commands`)

> [!INFO] Slash Command Structure
> discord.js provides a slash command builder to help us make slash commands.
> 
> ```javascript
> import { SlashCommandBuilder } from 'discord.js'
> 
> export const data = new SlashCommandBuilder()
>   .name('some command');
>   // can add more information about the slash command
> 
> export async function execute (interaction) {
>   // do something    
> }
> ```
> See `ping.js`, in `commands/utility` for a basic example.

> [!IMPORTANT]
> Every time you make a new slash command, or make changes to an existing slash command, make sure to run `node deploy-commands.js`.

> [!INFO] Adding Options (Inputs) to your commands
> use `.addStringOption()`, `addUserOption()`, etc. to let users give info to your slash command.
> A full list of ways to add information to a command can be found [here](https://discord.js.org/docs/packages/builders/1.11.2/SlashCommandBuilder:Class#addAttachmentOption)

> [!EXAMPLE]
> Here, our command is set to take a string input. The option is called `input`, has description `Text to repeat`, and cannot be empty.
> ```javascript
> import { SlashCommandBuilder } from 'discord.js';
> 
> export const data = new SlashCommandBuilder()
>     .setName('repeat')
>     .setDescription('Give a message to repeat!')
>     .addStringOption(option =>
>         option
>             .setName('input')
>             .setDescription('Text to repeat')
>             .setRequired(true));
> 
> export async function execute(interaction) {
>     const text = interaction.options.getString('input');
>     await interaction.reply(text);
> }
> ```
> Feel free to try this code!