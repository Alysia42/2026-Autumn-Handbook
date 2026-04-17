# Connect To AI with API

### Install The dotenv package
> [!TASK]
> 1. Run this command in the terminal`npm install dotenv --save` to download the dotenv package
> 2. Import the `.env` file -> `import 'dotenv/config'`

### Import the OpenAI API
> [!INFO] Info
> We need the OpenAI library and our API key to make requests. The key is stored in a variable called process.env

> [!TIP] Tip
> ```javascript
> import OpenAI from "openai";
> const apiKey = process.env.OPENAI_API_KEY
> ```

---

### Create the Client

> [!INFO] Info
> The client is how we talk to OpenAI.

> [!TIP] Tip
> ```javascript
> const client = new OpenAI({ apiKey });
> ```

---

### Send a Request to OpenAI

> [!INFO] Info
> - `client.chat.completions.create(...)` sends a message to the AI.
> - We use the `gpt-3.5-turbo` model for the basic text responses. (More models you can try: (OpenAI Models)[https://platform.openai.com/docs/models])
> - The input message goes inside `messages`.

> [!TIP] Tip
>
> ```javascript
> const response = await client.chat.completions.create({
>     model: "gpt-3.5-turbo",
>     messages: [{ role: "user", content: <Insert prompt here> }]
> });
> ```
