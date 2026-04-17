# What is the Discord API?

An **API** is a set of commands and operations, and instructions for how to encode them and where to send them, so that computers may talk to other computers.
Here, the **Discord API** allows us to communicate with the Discord web servers

There are two key components of the API:
* **Gateway events**&mdash;Your bot connects to the Gateway which is used for real-time communication between your bot and the Discord web servers.
 * Discord will alert your bot to things like messages being sent (`Message Create`), a user joining a server the bot is in (`Guild Member Add`), and most importantly, a user performaing a slash command (`Interaction Create`).
 * You can read the full list of events on the [Developer Portal documentation page](https://discord.com/developers/docs/events/gateway-events) or on the [discord.js documentation](https://discord.js.org/docs/packages/discord.js/14.21.0/Client:Class).
 * Your bot also needs to send ["heartbeats"](https://discord.com/developers/docs/events/gateway#sending-heartbeats) to the Discord Gateway, to signify that your bot is still online.
 You don't have to interact with this system though.

- **RPC**, over HTTP requests&mdash;This is the sort of thing you used yesterday.
To do things like send a message, your bot will make an HTTP request to the Discord web servers.
By sending a request in a certain format, you trigger a **remote procedure call** or (RPC).
Each operation that you do requires creating a separate HTTP connection.
Luckily, discord.js will handle that all for you.

There are lots of different applications that can interact with the Discord API, and bots are just one kind.
Bots are special because they are an app that gets a user account.
That means other users can interact with them like they are a user, such as giving them roles, sending them Direct Messages, and so on.
Bot users can be affected by permissions just as human users do.
Bots also need to continually indicate that they are online over a connection with the Gateway.

Other kinds of applications might use the Discord API through the Webhooks interface.
Those apps do not need to maintain a connection.

You can read all the gorey technical details abotu the API on the [Discord Developer Portal](https://discord.com/developers/docs/intro).

> [!TIP] I don't know what kind of bot to make!
> There are lots of websites online that gather lists of bots.
> Why not invite some to your server?
> That might give you some inspiration.
> * [discordbotlist.com](https://discordbotlist.com/)
> * [top.gg](https://top.gg/)
> * [discord.bots.gg](https://discord.bots.gg/)
