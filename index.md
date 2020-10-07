# Discord Bot Best Practices
If you are making a publically available bot, you should probably follow these best practices. The goal is to keep servers as clean as possible and their users as happy as possible!

**ALL BOTS SHOULD ALWAYS follow the Discord [Terms of Service](https://discord.com/terms), [Community Guidelines](https://discord.com/guidelines), and [Developer Policy](https://discord.com/developers/docs/policy).**

## All Bots Should...
- ❌ **NEVER** abuse the Discord platform in any way.
- ❌ **NEVER** modify a user's account in any way without **explicit permission from the user**.
- ❌ **NEVER** give targeted advertisements.
    - ❗ This includes DM advertising, such as randomly messaging a user with a link or ad.
- ❌ **NEVER** "scrape" data.
    - ❗ This includes logging more information than necessary to run the bot effectively.
    - ❗ This also includes collecting information on users for analytics purposes without their permission.
- ❌ **NEVER** sell or share a user's data in any way, except for communicating with an API to serve the user.
- ❌ **NEVER** retain data longer than necessary to run the bot effectively.
- ❌ **NEVER** knowingly serve children under the age of 13.
- ❌ **NEVER** do or encourage anything illegal.
- ❌ **NEVER** post anything with NSFW content outside of an NSFW channel in any way.
    - ❗ This includes DMing users NSFW content without their explicit permission.
- ❌ **NEVER** abuse an API in any way.
- ❌ **NEVER** mention users unless absolutely necessary.
- ❌ **AVOID** using common prefixes, or allow the user to set their own prefix.
    - ❌ **AVOID** using common prefixes, such as `!`, `$`, `?`, `.`, and `-`. These prefixes are common, and will likely overlap with other bots, causing several bots to attempt to do the same thing.
    - ❌ **NEVER** using `@` or `#` prefixes. Discord uses these characters to denote a user and channel mention, respectively.
        - ⭕ **EXCEPTION** a good practice is for your bot to use their mention as a prefix. For example, if my bot is called `Foobar` and has the `0001` tag, set the bot's prefix to `@Foobar#0001`.
    - ✔️ Use a unique prefix. This could be a prefix that pertains to your bot somehow, such as your bot's initials followed by a special character. For example, if your bot is called `Foobar`, you might want the prefix to be `fb!`.
    - ❌ **NEVER** use multiple prefixes. This increases the chance of a prefix collision.
        - ⭕ **EXCEPTION** if your bot's prefixes are a unicode prefix (`fb!`) and a mention (`@Foobar#0001`)
- ❌ **NEVER** respond with "invalid command". If a user sends a command that does not exist, **do not** reply with "invalid command". This just clutters up the channel.
- ✔️ **ALWAYS** respond "invalid arguments". If a user sends a valid command with invalid arguments, respond with more info about how to use that command.
- ✔️ **ALWAYS** respond **only** to explicitly invoked commands. Bots should not respond to normal chat messages not intended to invoke the bot.
    - ⭕ **EXCEPTION** Automod bots:
        - Automod bots should only take action on messages silently. If a message violates a rule and is deleted, it should be deleted without the bot posting a message in the channel.
        - If an automod takes an action, however, it **should always** be logged to a modlog.
        - The exception to this rule is if "extreme" action, such as kicking, banning, or muting, is taken, the user should be notified by DM if possible.
- ✔️ **ALWAYS** have an `info` command. This should provide basic info such as:
    - ✔️ The library used to run the bot, and what version.
    - ✔️ The usernames of the bot's creators.
    - ✔️ A link to the bot's support server. (If applicable)
    - ✔️ A link to the bot's website. (If applicable)
    - ✔️ Who to contact for questions or concerns.
- ✔️ **ALWAYS** ignore other bot's commands. Your bot **should not** reply to other bots. Read your library's docs to see how to do that.
- ✔️ **ALWAYS** allow the bot to respond to a mention. The response can be either a help message or a simple message telling the user what the bot's prefix is.
- ✔️ **ALWAYS** have error handling. If your bot encounters an error because of a ratelimit or invalid permissions, it should inform the user that there was an error and what the error was. It should **not** fail and crash silently.