<!-- PROJECT LOGO -->
</br>
<div align="center">

<a href="#readme.md"><img align="center" src="images/logo.png" alt="Logo" width="80" height="80"><a>

### 2bored2wait (UNOFFICIAL)

A proxy to wait out 2b2t.org's way too long queue.
This version of the code is not official, it is for private use. All that this private fork does is fix some bugs and make sure there is no backdoor.
Here is the original link to the project by themoonisacheese: https://github.com/themoonisacheese/2bored2wait

</div>

<!-- TABLE OF CONTENTS -->
<details open="open">
<summary>Table of Contents</summary><p>

1. [About The Project](#about-the-project)
   - [Built With](#built-with)
2. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
3. [How to use](#how-to-use)
4. [Configuration](#configuration)
5. [Roadmap and known issues](#roadmap-and-known-issues)

</p></details>

<!-- ABOUT THE PROJECT -->

## About The Project

A proxy to wait out 2b2t.org's way too long queue.  
Please Note that because of security reasons this tool doesn't auto-update! This is to prevent backdoors from newer code published from the official build of 2bored2wait.
2b2w does not show ETA from 2b2t. The ETA is calculated based on position in the queue. This results in better ETA most of the time.

### Built With

- node.js
- npm
- HTML
- css

<!-- GETTING STARTED -->

# Getting Started

To get a local copy up and running follow these simple steps.

## Prerequisites

Please optain all required items

- A discord bot (optional) ([detailed instructions](https://discordpy.readthedocs.io/en/stable/discord.html))

## Installation

### x86 and x64 (most home computers):

1. Read the code to ensure I'm not stealing your credentials. I'm not, but you shouldn't take my word for it. If you don't know how to read it, downloading stuff off the internet and giving it your password is probably a bad idea anyway.
2. Download the program [here](https://github.com/RegenixMC/2bored2wait/releases/latest)
3. Download and install [node.js](https://nodejs.org/) version 14 or above and [git](https://git-scm.com). You need git even if you download the repository as zip because it is to install the dependencies via npm.
4. Extract the folder to your desktop.
5. cd into the folder and run `npm install`.
6. (Optional) Take a look at `config/default.json`, edit your values and save.
7. Run `npm start`

### Other Platforms (including ARM / Raspberry Pi):

1. Download and install [node.js](https://nodejs.org/) version 14 or above and [git](https://git-scm.com). You need git even if you download the repository as zip because it is to install the dependencies via npm.
2. Open a terminal then clone this repo then cd into folder:

```sh
 git clone https://github.com/RegenixMC/2bored2wait
 cd 2bored2wait
```

3. Run `npm install` to install the required libraries
4. Start the program with `npm start`.

### Docker

1. Read the code to ensure I'm not stealing your credentials. I'm not, but you shouldn't take my word for it. If you don't know how to read it, downloading stuff off the internet and giving it your password is probably a bad idea anyway.
2. `docker run -d -p 80:8080 -p 25565:25565 -e NODE_CONFIG='{"username":"user@domain.com","mcPassword":"password","updatemessage":"n","BotToken":""}' 2bored2wait/2bored2wait:latest`. The docker image is automatically up to date after each push to this repo. Docker images are available for `amd64` and `arm64` among other platforms.
3. Open a browser and navigate to http://localhost
4. Press the "Start queuing" button. The queue position indicator auto-updates, but sometimes it takes a while to start counting (like 1 min).
5. Once the queue reaches a low number, connect to the Minecraft server at address `localhost`.
6. After you log off, click the "stop queuing" button. This is really important, as you will not actually disconnect from 2b2t until you do that.

If you want to change the configuration or you don't want your credentials in the bash history you will have to mount config/local.json manually.

# Configuration

- You can change all credentials in config/local.js or deleting that file.

# How to use

1. Read the code to ensure I'm not stealing your credentials. I'm not, but you shouldn't take my word for it. If you don't know how to read it, downloading stuff off the internet and giving it your password is probably a bad idea anyway.
2. Run `npm start`
3. It will now ask for your Minecraft email and password (or permission to use saved launcher data instead). If you want update messages then you need to type Y otherwise N. If you are using the discord bot you need to add your token. Then answer Y or N if you want to save your Minecraft credentials. If you answer N you will need to re-enter your Minecraft login information into the console each time you start the program.
4. Refer to Commands on how to use 2b2w from the console. Otherwise keep on reading for the web interface.
5. Now open a browser and navigate to http://localhost: your web port here (default 80).
6. Press the "Start queuing" button. The queue position indicator auto-updates, but sometimes it takes a while to start counting (like 1 min).
7. Once the queue reaches a low number, connect to the Minecraft server at address `localhost`.
8. After you log off, click the "stop queuing" button. This is really important, as you will not actually disconnect from 2b2t until you do that.

## Commands

All commands can be used through discord or simply typed in the console window.

- `start` will start the queue. It takes between 15-30 seconds for the bot to update with the queue position.
- `start 14:00` will start at 2pm. (Must use military time!)
- `play 8:00` will try to calculate the right time to join so you can play at 8:00
- `update` will send an update to the current channel with your position and ETA.
- `stop` will stop the queue.

<!-- ROADMAP -->

# Known issues

See the [open issues](https://github.com/RegenixMC/2bored2wait/issues) for a list of proposed features (and known issues).

- Starting the queue will revoke your Minecraft token. this means that you will not be able to join normal Minecraft servers until you restart the game
- If you connect after the queue is finished or reconnect the proxy will send cached data. Otherwise you would fly in an empty world. However not all data will be resend. You can move out of render distance (I find going through a nether portal works best) and return to fix this issue. Sometimes the client renders a cached chunk with a blank texture.
