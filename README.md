### Description
Workflow receives text via HTTP webhook.
If text length is less than 100 symbols, user receives an error message.
If text length is 100 symbols or more, text is summarized using LLM
and the result is sent to Telegram.

### Nodes used
- Webhook
- Edit Fields
- IF
- AI Agent (OpenAI Chat Model)
- Telegram

### Logic
- Text < 100 symbols → Telegram error message
- Text ≥ 100 symbols → LLM summary → Telegram

### How to test
Send POST request to webhook with JSON body:
```json
{
  "text": "Any long text"
}
