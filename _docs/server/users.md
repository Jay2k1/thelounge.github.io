---
layout: documentation
title: Users
description: Add your description here
category: Server
order: 2.2
---

# Users

Once you've set up your Shout server, it's time to add your first users. Open your `config.js` and set `public` to `false`. This will enable user login.

When you start Shout in "private" mode it will load every user found in your `users/` folder. Here's some of the features users get:

- All your IRC connections are kept alive
- Login and chat from multiple devices simultaneously

## Add users

To add a new user, run this command:

```
shout add <name>
```

This will create a new user in your `users/` folder.

_Note: By default, users are stored in the `~/.shout/users/` folder. You can change this location by changing the `home` setting (see [Configuration](/docs/server/configuration.html))._

## Edit users

Open the `user.json` for the specified user:

```
shout edit <name>
```

## Remove users

Simply run:

```
shout remove <name>
```

## List users

This command will print a list of all your existing users:

```
shout list
```

# User configuration

If you run `shout edit <name>`, the `user.json` file will open.

The user configuration is loaded upon server start. Here's an example of what a `user.json` file might look like:

```
{
  "user": "example",
  "password": "password",
  "log": false,
  "networks": [{
    "name": "Freenode",
    "host": "irc.freenode.net",
    "port": 6697,
    "tls": true,
    "password": "serverpw",
    "nick": "john",
    "realname": "John Doe",
    "commands": [
      "/msg NickServ identify password",
      "/msg ChanServ op #chan"
    ],
    "join": "#foo, #bar"
	}]
}
```