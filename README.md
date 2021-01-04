# CardiB-Rona-Telebot

I use this mini project as a playground to learn how to use telegram bot. Feel free to try my bot @CardiRonaBot on Telegram. The functionalities are simple:

1. Echoes whatever you say
2. Typing `/audio` sends back a random audio file to the user

# Webhook instead of polling

Much of the source code originates from [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot). However, instead of polling, I used webhook instead. This is because polling is inefficient and the data is not real-time while webhook can act as a push notification, removing the need to constantly check for updates on the Telegram server.

# Development

1. Install requirements: `pip3 install -r requirements.txt`

- You may also consider creating a virtual python environment.

2. Create an environment file: `touch .env`.

- Copy the contents over, similar to the template below.
- Use your own credentials. Remember to keep your token information private!

```bash
TOKEN=1456236133:BAEMGzl4H-ii69FLhmM799cegl2CnRULffk
URL=https://0511a20g14a3.ngrok.io
```

# Deployment

## Local

1. Download [ngrok](https://ngrok.com/download). Then run `./ngrok http 5000` on one terminal, and `python3 bot.py` in another terminal.

- This opens up your local port to the public, which allows for external requests to be forwarded to your `localhost` endpoint. This is very useful for quick debugging.
- `localhost` should work fine too if you are testing on the same network.

## Cloud

For production, I used [heroku](heroku.com) instead of ngrok. This way, you don't have to leave your terminal running. And the best part is that heroku is free to use!

- Make sure to add the `Config Vars` key-value pairs, namely `TOKEN` and `URL`.
- The `URL` will now take the form of `https://cardib-rona-telebot.herokuapp.com`.
