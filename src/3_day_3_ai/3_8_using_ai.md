# Use The AI Response
### Access the AI’s Reply

> [!INFO] Info
> The response object has a nested structure. To access just the text reply:

> [!TIP] Tip
>
> ```javascript
> response.choices[0].message.content
> ```

---

### Use a Variable as Input

> [!INFO] Info
> You can store the question as a variable and use it in the API call.

> [!TIP] Tip
>
> ```javascript
> const userPrompt = "What is AI?";
>
> const response = await client.chat.completions.create({
>     model: "gpt-3.5-turbo",
>     messages: [{ role: "user", content: `${userPrompt}` }]
> });
> ```

---

### Define an `async` Function

> [!INFO] Info
> `async` means this function can use `await` inside it.

> [!TIP] Tip
>
> ```javascript
> async function askOpenAI(prompt) {
>     const response = await client.chat.completions.create({
>         model: "gpt-3.5-turbo",
>         messages: [{ role: "user", content: prompt }]
>     });
>     return response.choices[0].message.content;
> }
> ```

---

### Use the AI Reply in Your Command

> [!INFO] Info
> Replace your original `interaction.reply()` with a call to your AI function.

> [!TIP] Tip
>
> ```javascript
> const answer = await askOpenAI(userPrompt);
> await interaction.reply(answer);
> ```

