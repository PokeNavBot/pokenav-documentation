# Trading

## Commands

```eval_rst
.. csv-table:: Announcing and Coordinating Trades
   :header: "Command", "Who", "Where", "Description"
   :widths: 15, 10, 10, 20

   ``$set-trainer-code 1234 1234 1234``, Anyone, Anywhere, "Sets a trainer code in the users profile."
   ``$stc 1234 1234 1234``, Anyone, Anywhere, "Sets a trainer code in the users profile."
   ``$get-trainer-code IVpips``, Anyone, Anywhere, "Gets a trainer code in the users profile (can be copy and pasted)."
   ``$gtc IVpips``, Anyone, Anywhere, "Gets a trainer code in the users profile (can be copy and pasted)."
   ``$want togepi``, Anyone, Trade Lobby, "Asking for a togepi -- no specifications."
   ``$want togepi shiny``, Anyone, Trade Lobby, "Asking for a shiny togepi."
   ``$want togepi gender:male``, Anyone, Trade Lobby, "Looking for a male togepi."
   ``$want togepi gender:female``, Anyone, Trade Lobby, "Looking for a female togepi."
   ``$want togepi gender:female shiny``, Anyone, Trade Lobby, "Looking for a shiny female togepi."
   ``$want gengar "move:shadow claw"``, Anyone, Trade Lobby, "Looking for a Gengar with shadow claw."
   ``$want Exeggutor-Alola``, Anyone, Trade Lobby, "Looking for an exeggutor (alolan form)."
   ``$want Unown-F``, Anyone, Trade Lobby, "Looking for an Unown (F form)."
   ``$want Unown "note: A B or C forms"``, Anyone, Trade Lobby, "Looking for an Unown with notes for broad specification."
   ``$unwant 13``, Anyone, Anywhere, "Deletes trade request with Trade #13 in header."
   ``$clear-wants``, Anyone, Anywhere, "Deletes all your trade requests."
```

## Terminology

#### Active Trades

This is a channel where all trades on your server appear. If created by the PokeNav, it is not readable by users and contains a clean copy of all outstanding trade requests.

#### Trade Lobby

Trade lobby is like a raid lobby. Simply put, its a channel where you may announce trades. 

## Features

### Announcing a Trade

You announce a trade with the `$want` command. Its most basic form typically takes a Pokemon's form name, like "Togepi", "Mewtwo" or "Exeggutor-Alola". Form names in PokeNav never have punctuation. When you provide them, if the form contains a space, you must surround it with quotes.

PokeNav is designed to make it easy to request a trade for a Pokemon. If you need to get specific, you can add modifiers. Modifiers are typically a "keyword:value". Sometimes the value is optional. Valid modifiers are:

* `shiny` - Indicates that you want the shiny form.
* `gender:male` - Indicates you want a certain gender (valid values are male, female, m, f, none).
* `move:shadow claw` - Indicates you want a specific move. Move must be in PokeNav's movedex (i.e. in the game master file).
* `note:ash hat / witch hat` - Indicates you are adding a note to specify a special attribute or constraint PokeNav doesn't support. For example hat pikachus or level requirements.

PokeNav only uses the space required if you need a specific modifier. So if you don't specify any moves, PokeNav won't show you moves in the announcement.

The order of modifiers doesn't matter. You can provided all of them or none. If the modifier value has a space, always surround it the entire thing with quotes.

### Limits

You can have up to 3 outstanding trade requests in PokeNav at once.

Trade requests last for at most 3 days, then disappear.

PokeNav will only notify the poster once per individual showing interest in a post. This prevents using PokeNav to spam posters with responses.

### Responding To A Trade

Trades happen asynchronously. If you see a trade you want to help with, react to the messaged as indicated. The poster will be DM'd by PokeNav to add your friend information and send you a DM to coordinate the trade. 

```eval_rst

.. note::
    
    Bots in discord cannot create DMs for users or participate in group DMs, so PokeNav acts like an inbox for coordinating trades.
```

### Clearing Trades 

When a trade is agreed upon and you no longer need any that Pokemon, you may react to the message with the red X reaction. This will clear all your trade announcements for that trade. You can also clear your trades using `$unwant 14` if 14 is the trade id from any channel or a DM. You can also clear all your trades using `$clear-wants` (though it will clear all your trades on any server). 

Doing this will allow you to request another trade if you'd like.
