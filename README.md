<p align="center">
    <img src="https://discord.js.org/static/logo-square.png" height="280" />
    <h1 align="center">~ discord bot template ~</h1>
    <strong>
         <p align="center">
              A discord bot template for <a href="https://discord.js.org">discord.js</a>.
         </p>
    </strong>
</p>

---


## Basic Information

This repo houses my discord.js bot template. I'll warn you that my coding style is kinda weird and I change it pretty often. So this might not match your style. 

## Requirements 

<kbd><img src="./.img/node.png" height="20"/></kbd> **NodeJS Version:** ^15.5.0+<br/>
<kbd><img src="https://discord.js.org/static/logo-square.png" height="20"/></kbd> **Discord.js Version:** ^12.5.1+

## Folder Hirachy

| folder/file  | purpose | description |
| -------------  | ------------- | ------------- |
| `config.js` | default config dir | can be changed in the `src/index.js` file |
| `src/index.js` | main bot file | should not be changed |
| `src/Bot/*` | main source | all new files can be added in the sub folders |
| `src/Bot/Commands/*` | command files | new commands will be autoloaded by name |
| `src/Bot/commandHandler.js` | command handle | should not be changed ~ _depends on the usage of the bot_ |
| `src/Bot/index.js` | init bot source | should be changed to fit your needs |

You can find a `index.js` in any of the subfolders of the `src` folder. These are meant for the main code of the given section.

## Code Style

- The code is heavily object-based without any non-object variables.
- All temporary created "variables" are defined in the current `this` object of the class and deleted using `delete this.[var]` after they were used.
- The first character of "top-level" objects or variables are uppercase and the rest is lower- & camelcase. 
Code outside a function is to be avoided.

## Issues or Pull Request

**I won't accept any pull requests or answer any issues since this is a personal template.**

## Usage

1. Clone the repo `git clone https://github.com/13ace37/surftimer-bot.git REPOSITORY`
1. Change remote orign `git remote set-url origin https://github.com/USERNAME/REPOSITORY.git`
1. Make your changes

## Disclaimer

**This project is licensed under the MIT License.**

I do not take responsibility for any of your bots. 
You are free to use this template as long as you follow the MIT License and so keep my name somewhere in your project.

© Riccardo "ace" H. 2021