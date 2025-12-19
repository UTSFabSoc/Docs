This bot is designed to catch and remove classic discord scam messages
### How does it work
For each message sent, pounce calculates a "heat" score which represents how confident it is that the message is a scam. Heat is accumulated in a few ways:
- Trigger words - the bot maintains a list of words that it associates with scams, each word has a different contribution to the heat value depending on how specific it is, the full list is displayed below
- Attachment count - Each attachment added to the message contributes an additional 0.5 heat
Should a message reach a threshold of **7** heat, pounce will trigger forwarding a copy of the message to the repots channel (set by using `/set-report-channel`), deleting the original and timing out the user unless they are immune

### What makes someone immune
- Having a role that grants immunity (provided by `/add-immune-role`)
- Having sent 30 messages to a server
- Having sent 10 messages to a server and having been on the server for at least a week

## Commands 
- `/set-report-channel` Causes pounce to send reports to the channel this is run in
	- Make sure pounce has access to the channel
	- If this is not set, then pounce will send reports in the same channel where the suspicious message is sent
- `/add-immune-role` Provides immunity to the selected role
- `/remove-immune-role` Removes immunity from the selected role

## List of Trigger Words
all matches are case insensitive, each word may match multiple times per user sent message

| match                  | heat |
| ---------------------- | ---- |
| macbook                | 1    |
| free                   | 2    |
| give out               | 1    |
| dire need              | 2    |
| macbook air            | 2    |
| charger                | 1    |
| give it out            | 1    |
| giving it out          | 1    |
| giving out             | 1    |
| new model              | 2    |
| @everyone              | 5    |
| @here                  | 3    |
| first come first serve | 2    |
| strictly               | 1    |
| iphone                 | 0.5  |
| ps5                    | 0.5  |
| @gmail.com             | 1.5  |
| canon                  | 2    |
| camera                 | 2    |
| invest                 | 1    |
| free nitro             | 5    |
| nitro                  | 1    |
| free steam             | 5    |
| bitcoin                | 2    |
| btc                    | 2    |
| crypto                 | 1.5  |
| **                     | 2    |
| https://imgur.com      | 3    |
| https://               | 1    |
| http://                | 2    |
| (per image)            | 0.5  |
| (per image - no text)  | 3    