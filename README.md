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

The bot can be started by using `node src/index.js {token}` - the token in the config file will overwrite the command line argument!

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

### Logging

I provide a custom logger using `this.Client.Logger`. This class holds 3 functions and they represent 3 log "levels": `log, warn, err`.
The log files are created in the root folder under `/logs` and are named `out-{date}.log` and `err-{date}.log`. The "err" one hold the warnings and errors and the rest goes to the "out" one.


Example:

```js

// The logID is saved internally and get increased for each log starting at 1.
this.Client.Logger.log("Connected to the server!"); // expected output: LOG  ~ [DATE] [TIME] #1: Connected to the server! 
this.Client.Logger.log("Connected to the server!"); // expected output: LOG  ~ [DATE] [TIME] #2: Connected to the server!
this.Client.Logger.log("Connected to the server!", 773); // expected output: LOG  ~ [DATE] [TIME] #773: Connected to the server!  

// The logID only effects the .log() function the .warn() and .error() function print 0 or the one you provide.
this.Client.Logger.warn("Connection not stable!"); // expected output: WARN ~ [DATE] [TIME] #0: Connection not stable!
this.Client.Logger.warn("Connection not stable!", 34); // expected output: WARN ~ [DATE] [TIME] #34: Connection not stable!

// The logID only effects the .log() function the .warn() and .error() function print 0 or the one you provide
this.Client.Logger.error("Not connected to the server!"); // expected output: ERR  ~ [DATE] [TIME] #0: Not connected to the server!
this.Client.Logger.error("Not connected to the server!", 21); // expected output: ERR  ~ [DATE] [TIME] #21: Not connected to the server! 

```

### Commands

The command name is defined by the filename. If you want a `!hello` command, you'll need to create a file named `hello.js` in the `src/Bot/Commands/` folder.

Template:


```js
let Command = require("."); //gets the default Command class

module.exports = class extends Command {
	// must be defined - returns a string with the description of the command function
	// can also return false - gets replaced with N/A
	getInfo() { 
		return "says hello and thanks the user";
	}
	// must be defined - runs if users types the command
	/* expected result: 
		Bot: Hello I'm a bot.
		Bot: @User, thanks for using this bot.
	*/
	run() {
		this.send("Hello I'm a bot.");
		this.reply("thanks for using this bot.");
	}
}
```

Default functions/variables:

```js
this.message 		// message object returned from onMessage event
this.Client 		// discord bot client object


this.send(message)	// sends a normal message in the channel where the command got executed

// replies to the user with a tag in the channel where the command got executed
// Format: @user, {message}
this.reply(message)
```

## Code Style

- The code is heavily object-based without any non-object variables.
- All temporary created "variables" are defined in the current `this` object of the class and deleted using `delete this.[var]` after they were used.
- The first character of "top-level" objects or variables are uppercase and the rest is lower- & camelcase. 
Code outside a function is to be avoided.

## Issues or Pull Request

**I won't accept any pull requests or answer any issues since this is a personal template.**

## Usage

1. Fork or clone the repo `git clone https://github.com/13ace37/surftimer-bot.git REPOSITORY`
1. Change remote orign `git remote set-url origin https://github.com/USERNAME/REPOSITORY.git`
1. Make your changes

## Disclaimer

**This project is licensed under the MIT License.**

I do not take responsibility for any of your bots. 
You are free to use this template as long as you follow the MIT License and so keep my name somewhere in your project.

© Riccardo "ace" H. 2021
