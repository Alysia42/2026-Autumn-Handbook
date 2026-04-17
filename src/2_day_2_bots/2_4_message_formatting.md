## Task 1: Creating a Basic `/ping` Command

We can start by making a command that replies with `"Pong!"` when the user types `/ping`.

### Code

```js
const { SlashCommandBuilder } = require('discord.js');

module.exports = {
  data: new SlashCommandBuilder()
    .setName('ping')
    .setDescription('Replies with Pong!'),
  async execute(interaction) {
    await interaction.reply('Pong!');
  },
};
```

### Explanation

- `SlashCommandBuilder` is used to define your slash command (`/ping`).
- The `module.exports` object contains:
  - `data`: Defines the command name and description.
  - `execute`: The function called when the command runs.

## Task 2: Formatting Bot Messages

Discord.js provides built-in formatting tools to stylize your bot’s messages.

### Example

```js
const { blockQuote, bold, italic, quote, spoiler, strikethrough, underline, subtext } = require('discord.js');
const string = 'Hello!';

const boldString = bold(string);
const italicString = italic(string);
const strikethroughString = strikethrough(string);
const underlineString = underline(string);
const spoilerString = spoiler(string);
const quoteString = quote(string);
const blockquoteString = blockQuote(string);
const subtextString = subtext(string);
```
### Combine Styles

You can nest formatting functions for more expressive messages:

```js
const message = bold(italic("This is bold and italic!"));
await interaction.reply(message);
```

### Emphasizing Bot Responses

Use formatting to emphasize context:

```js
await interaction.reply(blockQuote(bold("System Message: ") + "Command executed successfully."));
```

Or for dramatic or humorous effect:

```js
await interaction.reply(spoiler("Secret message inside..."));
```

### Usage in Commands

To make the reply bold in your `/ping` command:

```js
await interaction.reply(bold('Pong!'));
```

You can also:
- Italicize with `italic('Pong!')`
- Make it a spoiler with `spoiler('Pong!')`
- Use other formatting methods above


## Task 3: Pinging a User

Now we will update the `/ping` command to mention a specific user.

### Updated Command

```js
const { SlashCommandBuilder } = require('discord.js');

module.exports = {
  data: new SlashCommandBuilder()
    .setName('ping')
    .setDescription('Ping a user!')
    .addUserOption(option =>
      option.setName('target')
        .setDescription('User to ping')
        .setRequired(true)
    ),
  async execute(interaction) {
    const user = interaction.options.getUser('target');
    await interaction.reply(`Pong! ${user}`);
  },
};
```

### Explanation

- `addUserOption`: Adds a required user input to the command.
- `interaction.options.getUser('target')`: Retrieves the user selected.
- `${user}`: Automatically converts to `@mention`.


- You’ve created a basic `/ping` command.
- You learned how to stylize bot messages using Discord.js utilities.
- You enhanced the command to ping specific users.

