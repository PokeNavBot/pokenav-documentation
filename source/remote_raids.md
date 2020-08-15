# Remote Raids

```eval_rst

.. note:: 
    
    This is a new feature available in 1.82.0, therefore these documents and the feature set is subject to change.

    Please provide feedback and we will adjust the feature set and make an awesome tool for remote servers.

```
## Motivation

PokeNav, at the time of this writing, is a 2+ year old project that has always been focused around local communities. Many of the assumptions and features are designed with local communities and in-person raids in mind.

Remote Raids are an attempt to optimize PokeNav-style raid coordination for large, remote-only servers. Often these servers have too much activity for the large number of actions PokeNav performs when raids are created and hit rate limits. 

Remote Raids also help local servers if they want to setup channels for locally coordinating remote raids.

## Highlights 

Remote Raids simplifies raid coordination and adds features that are useful for remote only servers. Remote raid channels are just like regular raid channels exception for the following key differences:


- **Limited to 6 trainers**; this is not customizable.
- **Tied to the host**; if the host leaves, the raid ends immediately.
- **Smaller announcement messages** 
- **Localized to all user**; the expiration or raid end time shows in the footer in the user's local timezone instead of the server's timezone
- **Remote only joins**; All trainers join remotely and are marked as invited by the host automatically.
- **Easy friendship**; Host trainer code is shown in the top embed and users can type `$htc` to get the hosts code in-channel.
- **Shows the user's country in the embed if no gym is matched.**
- **Do not create roles for raids**, which eliminates the possibility of hitting the discord role creation rate limit for bots.

## Benefits

As remote raids do less when raids are created, they create faster and are more scalable in large servers. They cut down on the number of actions users have to take when you know they are raiding remotely.

## Limitations

Bots and webhooks cannot create remote raids.

The `onsite`, `remote` and `remote i` commands are disabled for remote raids.

## Getting Started

If you are a remote only server, you can get convert all your raid lobbies into remote raid lobbies using `$toggle all-raid-lobbies-remote`. 

If you are in a local server, you can toggle a channel into a remote raid lobby using `$toggle remote-raid-lobby #channel`.

### Remote Raid Lobbies

Remote raid lobbies are just like regular raid lobbies, but all `$raid` commands will create remote raids instead of regular raids. If you don't like remote raids, you can go back to the old behavior by running the toggle command again.

You can still make remote raids in a regular lobby if you make a raid with `$remote-raid` or `$rr` instead of the normal raid command.

`$show settings` will show your remote lobbys with a globe next to them.

```eval_rst

.. note:: 

    You do not need to user the `$rr` command to make a remote raid. All raid commands make remote raids in a remote raid lobby. Use `$rr` to test out remote raids in a regular lobby.

```

### Country Integration

As a remote server you will probably have a better experience if you instruct your users to set their country with `$set country USA`, for example. Supports the name of the country or its country code using a fuzzy search.

<img src="/_static/imgs/set-country.png" />

This country will be displayed in the remote raid embed.

<img src="/_static/imgs/remote-raid-announcement.png" />


### Host Trainer Code

The hosts trainer code is shown in the top level message:

<img src="/_static/imgs/remote-raid-in-channel.png" />

Additionally, you can type `$htc` to easily get a copy of the host trainer code which can be pasted into the game.

<img src="/_static/imgs/htc.png" />


## Commands

```eval_rst
.. csv-table:: Commands Specific To Remote Raids
   :header: "Command", "Who", "Where", "Description"
   :widths: 15, 10, 10, 20

   ``$toggle remote-raid-lobby #channel``, Anyone, Moderation Channel, "Turns a channel into a remote raid lobby."
   ``$toggle all-raid-lobbies-remote``, Anyone, Moderation Channel, "Turns all your raid lobbies into remote raid lobbies."
   ``$rr genesect``, Anyone, Raid Lobby, "Creates a remote raid in a regular raid lobby."
   ``$rr genesect starbucks 35``, Anyone, Raid Lobby, "Creates a remote raid in a regular raid lobby."
   ``$htc``, Anyone, Remote Raid Channel, "Returns a copyable trainer code for the host."
   ``$set country usa``, Anyone, Anywhere, "Sets your location to be displayed in remote raid announcements."

```

