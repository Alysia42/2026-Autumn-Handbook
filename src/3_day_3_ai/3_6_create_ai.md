# Create A New AI Slash Command

**Now we want to be able to call the Open AI using our Discord bot. Here we will implement a new slash command: `/ask`.**

---
> [!INFO] Info
> Slash commands let you trigger bot responses using a `/command` in Discord.

> [!SUCCESS] Task
> 1. Create a new file called `ai.js` in the `commands/utilities` folder.
> 2. Create a nre slash command for the AI wrapper

> [!TIP] Tip
> ```javascript
> import { SlashCommandBuilder } from 'discord.js'
> export const data = new SlashCommandBuilder()
>  .setName('some command');
>  // can add more information about the slash command
>
> export async function execute (interaction) {
>  // do something    
>
> }
>
> export { data, execute };
> ```
