# Getting Started app for Discord

This project contains a basic Discord app written in JavaScript, built base on the [getting started guide](https://discord.com/developers/docs/getting-started).

## Project structure
Below is a basic overview of the project structure:

```
├── .env        -> sample .env file
├── app.js      -> main entrypoint for app
├── commands.js -> slash command payloads + helpers
├── utils.js    -> utility functions and enums
├── package.json
├── README.md
└── .gitignore
```

## Running app locally

Before you start, you'll need to install [NodeJS](https://nodejs.org/en/download/) and [create a Discord app](https://discord.com/developers/applications) with the proper permissions:
- `applications.commands`
- `bot` (with Send Messages & Read messages & Read chat history enabled)

Configuring the app is covered in detail in the [getting started guide](https://discord.com/developers/docs/getting-started).

### Setup project

First clone the project:
```
git clone https://github.com/Oja95/discord-transcribe-bot.git
```

Then navigate to its directory and install dependencies:
```
cd discord-transcribe-bot
npm install
```

### Get app credentials

Fetch the credentials from your app's settings and add them to a `.env` file (see `.env.sample` for an example). You'll need your app ID (`APP_ID`), bot token (`DISCORD_TOKEN`), and public key (`PUBLIC_KEY`).
Fetching Discord credentials is covered in detail in the [getting started guide](https://discord.com/developers/docs/getting-started).

It is also possible to configure custom listening port for the HTTP server by setting the `PORT` environment attribute.

Additionally, this bot implementation relies on the [DeepInfra Automatic Speech Recognition AI model](https://deepinfra.com/openai/whisper-large/api), communicating it via API. One must configure `DEEPINFRA_API_KEY` token obtained from the said site.


### Install slash commands

The commands for the example app are set up in `commands.js`. All of the commands in the `ALL_COMMANDS` array at the bottom of `commands.js` will be installed when you run the `register` command configured in `package.json`:

```
npm run register
```

### Run the app

After your credentials are added, go ahead and run the app:

```
node app.js
```

> ⚙️ A package [like `nodemon`](https://github.com/remy/nodemon), which watches for local changes and restarts your app, may be helpful while locally developing.

## Other resources
- Read **[the documentation](https://discord.com/developers/docs/intro)** for in-depth information about API features.
- Browse the `examples/` folder in this project for smaller, feature-specific code examples
- Join the **[Discord Developers server](https://discord.gg/discord-developers)** to ask questions about the API, attend events hosted by the Discord API team, and interact with other devs.
- Check out **[community resources](https://discord.com/developers/docs/topics/community-resources#community-resources)** for language-specific tools maintained by community members.
