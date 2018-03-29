ZNC Push via Telegram
=====================

This section contains the specific steps to configure for [Telegram][] after you install the
module by following the above steps.

* First of all, you need to have a telegram account.
* Talk to [BotFather][] to create a new bot and get an api key.
* Create a chat with the bot and say something in the chat.
* Obtain your chat_id (a numeric id # used internally) one of two ways
  * Use browser to connect to https://api.telegram.org/bot[apikey]/getUpdates (replace the apikey with
  the key generated by BotFather). You should see messages sent from you, and there will be several
  id fields in the reply. We'll use the one in the chat session.
  * Chat with @get_id, and send it the command /my_id. It will respond with your chat_id
* set service to 'telegram': <code>/msg *push set service telegram</code>
* set secret to the **api key**: <code>/msg *push set secret your-api-key</code>
* set target to chat ID: <code>/msg *push set target your-chat-id</code>

You can style your messages with [basic HTML][HTML] when you set the
`message_escape` option accordingly.

    set message_escape HTML
    set message_content <i>{context}</i>: &lt;<b>{nick}</b>&gt; {message}

[Telegram]: https://telegram.org
[BotFather]: https://core.telegram.org/bots#6-botfather
[HTML]: https://core.telegram.org/bots/api#formatting-options