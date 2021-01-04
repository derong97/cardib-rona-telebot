# CardiB-Rona-Telebot

I use this mini project to learn how to use telegram bot. Click on this [link](https://t.me/CardiRonaBot) to test my bot @CardiRonaBot - idea inspired from this [video](https://www.youtube.com/watch?v=tmULzkCb9AQ).

The functionalities are simple:

1. Echoes whatever the user says
2. Typing `/audio` sends back a random audio file

# Webhook instead of Polling

Much of the source code originates from [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot). However, instead of polling, I used webhook instead. This is because polling is inefficient and the data is not real-time while webhook can act as a push notification, removing the need to constantly check for updates on the Telegram server.

# Development

1. Get the Telegram bot API token from [BotFather](https://t.me/botfather)
2. Download source code and install requirements: `pip3 install -r requirements.txt`

- You may also consider creating a virtual python environment.

3. Create an environment file: `touch .env`.

- Copy the contents over, similar to the template below.
- Use your own credentials. Remember to keep your token information private!

```bash
TOKEN=1456236133:BAEMGzl4H-ii69FLhmM799cegl2CnRULffk
URL=https://0511a20g14a3.ngrok.io
```

# Deployment

## Local

1. Download [ngrok](https://ngrok.com/download).
2. Run `./ngrok http 5000` on one terminal. Copy the link and replace the value for the `URL` field in the `.env` file.

- This opens up your local port to the public, which allows for external requests to be forwarded to your `localhost` endpoint. This is very useful for quick debugging.
- `localhost` should work fine too if you are testing on the same network.

3. Run `python3 bot.py` on another terminal.

- Your bot should be working now.

## Cloud

For production, I used [heroku](heroku.com) instead of ngrok. This way, you don't have to leave your terminal running. And the best part is that heroku is free to use!

- Make sure to add the `Config Vars` key-value pairs, namely `TOKEN` and `URL`.
- The value in the `URL` field will take the form like so: `https://cardib-rona-telebot.herokuapp.com`.
