# Events and Listeners



> [!IMPORTANT] What's an Event?
> An event is something that happens in your Discord server, like someone sending a message, joining a voice call, or a new user joining.
> When you want your bot to notice when these things happen, you can use listeners!

> [!INFO] Listeners = Bot Ears
> Listeners are like the eyes and ears of your bot. They listen for certain events, and when they "hear" one, you can tell your bot to do something, like send a reply or welcome a new member!

> [!TIP]
> All code for events is to be put in its own file, in the `events` folder.

> [!EXAMPLE]
> Suppose you want a bot to repeat every message.
> ```javascript
> import { Events } from 'discord.js';
> 
> const name = Events.MessageCreate;
> const once = false;
> function execute(message) {
>   // Prevent the bot from copying its own messages or other bots
>   if (message.author.bot) return;
> 
>   // Send the same content back to the channel
>   message.channel.send(message.content);
> }
> 
> export { name, once, execute };
> ```
> 
> Here, `Events.MessageCreate` is the event, which triggers when someone sends a message in the server.
>
> The value `once` has been set to false, as we want this event to trigger more than just one time.
> 
> If you want your bot to run something only once (the first time only), you can set `once` to `true`. An example can be seen in `clientReady.js`, which prints a message in the terminal once when starting the bot.

> [!WARNING] Possible errors
> In the above code, you may get an error "Used disallowed intents". If so, it is likely that your bot is trying to read messages, but is not allowed to by discord.
>
> To fix this, go to the discord developer site for your bot, go to the Bot section on the sidebar, and enable "MESSAGE CONTENT INTENT". Also, in `index.js`, replace 
> ```javacript
> const client = new Client({ intents: [GatewayIntentBits.Guilds] });
> ```
> with 
> ```javascript
> const client = new Client({ 
> 	intents: [
> 		GatewayIntentBits.Guilds,
> 		GatewayIntentBits.GuildMessages,
> 		GatewayIntentBits.MessageContent
> 	]
> });
> ```

> [!INFO] There are many events!
> Your bot can listen for many events, like messages, member joins, reactions, and more!
> 
> Want to see them all? In VSCode, if you type `Events.` (with the dot), you will see a long list.
>
> Or, you can visit [the official discord.js website](https://discord.js.org/docs/packages/discord.js/main/Client:class) for more information. In the **Events** section, each event has a description of how it triggers, and what information your bot will receive.

> [!SUCCESS] Try This!
> Your task is to make your bot react to a message with an emoji 👋 when someone says "hello".
> 1. Create a new file in the `events` folder called `hello.js`.
> 2. The bot should listen to every message
> 3. The bot should be able to run many times
> 4. It should check if a message contains the word "hello", and react to the message if so.

> [!HINT]
> You can check if a message contains a word by checking if `message.content.includes('word')`

> [!HINT]
> You can react to a message using `message.react('👋')` (can copy the emoji).