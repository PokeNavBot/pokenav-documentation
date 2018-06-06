# Raiding

## Commands

```eval_rst
.. csv-table:: Announcing and Coordinating Raids
   :header: "Command", "Who", "Where", "Description"
   :widths: 15, 10, 10, 20

   ``$raid latios Starbucks``, Anyone, Raid Lobby, "Starts a latios raid party for Starbucks."
   ``$exraid mewtwo Burpee Park``, Anyone, EX Raid Lobby, "Starts a mewtwo ex raid party for Burpee Park"
   ``$boss latios``, Creator / Moderator, Raid Party, "Changes the raid boss to latios."
   ``$counters``, Anyone, Raid Party, "Gets the counters for the raid boss."
   ``$counters windy``, Anyone, Raid Party, "Gets the counters for the raid boss in windy weather"
   ``$end``, Creator / Moderator, Raid Party, "Immediatelly ends the raid."
   ``$here``, Anyone, Raid Party, "Marks you as having arrived at the raid."
   ``$here @IVpips @koshermuffin``, Anyone, Raid Party, "Marks IVpips and koshermuffin as having arrived at the raid."
   ``$leave``, Anyone, Raid Party, "Leaves the raid party immediatelly."
   ``$address 123 Main St``, Anyone, Raid Party, "Sets the location of the raid."
   ``$gym Deep Meadow Park``, Anyone, Raid Party, "Sets the location to the gym in your play area."
   ``$time``, Anyone, Raid Party, "Gets the time remaining until egg hatch, raid end and channel expiration."
   ``$members``, Anyone, Raid Party, "Gets the list of members participating in the raid."
   ``$reset``, Creator / Moderator, Raid Party, "Resets everyones arrival status."
   ``$status``, Creator / Moderator, Raid Party, "Updates the public status of the raid party."
   ``$with``, Anyone, Raid Party, "Sets your companion accounts for this raid."
   ``$where``, Anyone, Raid Party, "Gets the current location of the raid."
```

## Terminology

#### (EX) Raid Lobby

A channel that the discord server moderators have enabled to allow for raid or ex raid announcements. Raid commands are not allowed in a channel unless expicilty enabled by making it a raid lobby, allowing you to ignore PokeNav's raid coorindation features, if you so choose.

A channel can be configured for Raids, EX Raids or Both. See community setup for details.

#### Raid Party

A channel / role that exists for the purposes of coordinating raids. Certain commands are only allowed inside a raid party's channel.


## Features

```eval_rst

.. note::
    
    Complete documentation coming shortly...
```

### Announcing a Raid

With PokeNav, announcing and coordinating a raid is PokeNav is trivial.

While several methods of announcing raids exist, All of these methods require being in a "raid lobby" which is simply a channel that has been enabled for annoucing raids. They will not work outside a raid lobby.

#### $raid command

The `$raid` command with no arguments will create a bare bones channel for coordination. This channel will last for up to 2 hours by default (can be set by server admins).

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/It2L-DTlKSc" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

#### $exraid command

The `$exraid` command with no arguments will create a bare bones channel for coordination. This channel will last for up to 14 days by default (can be set by server admins).

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/PCCrBiMa7b0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

#### via raid roles

Your server admin can designate roles that will automatically trigger a raid channel when used in a message in a raid lobby.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/LkqH6tqvj60" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

#### via screenshot

Drop a screenshot of a raid and PokeNav will automatically scan it and create a raid lobby. 

The hatch time, end time and expiration will all be based off the timestamps in the screenshot. 

The boss will be automatically detected using a combination of text recognition and image recognition (even if the bosses name is obscured). 

If your servers play area has gyms loaded into PokeNavs database, the location will automatically be set based on the name of the gym and directions will be made available.

### Raid Screenshot Scanning

When uploading screenshots, help PokeNav accurately extract information from the screenshot. Make sure the gym and boss name are visible if possible.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/RDYo9PvIGzo" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

### EX Raid Pass Scanning

EX raid passes also work, make sure you upload a full screenshot of the pass with all information visible.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/u5sQeg44Xkg" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

### Joining a Raid

All raid channels are private by default (only admins can see them). Scroll up in your raid lobby or see the active-raids channel for a complete list of raids. React with a person icon to any message that mentions a raid and you will be added to the party.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/41q29YlLoKk" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

### Updating the Boss

If the channels boss isn't set, use the `$boss` command to set it. PokeNav doesn't care about the boss if its an egg at the moment, so if its an egg, wait until the boss is known to set it.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/8G5JSnZTciw" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

### Leaving the Raid

If you joined accidently or can't make it, use the `$leave` command to leave the raid. You will be removed from the channel and the raid party members list.

Don't leave a raid after its done or you won't get join credit in your profile and leaderboard for having participated. Instead just wait for it to expire or the creator to end the raid.

### Listing Raid Party Members

You can view all the participants of the raid by typing `$members` or `$m`. It will show all the members, companion accounts and who has arrived on site.

### Promoting a Raid

Need a little bit of extra help? Go into any channel where PokeNav can read and write and mention the channel for your raid party. PokeNav will add a reaction and others can join right from another channel.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/hQEVWXoQYmk" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```
### Updating Status

Status is the a globally visible message that indicates what is happening in the raid right now. Use it to indicate the next step, such as "Double, first starts at 1:15pm, then 1:30p" or "Hard start at 1:45pm". 

Status updates are visible inside the raid and in the raid advertisement.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/4i_f5YZLAFQ" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```
### Arriving at a Raid 

When you arrive at a raid, you can use the `$here` command to mark yourself as having arrived. This will make it easy to get an at-a-glance view of who is missing, so no one is left out.

### Ending a Raid

When the raid is over, creators or raid moderators can clean up the raid and reduce noise by using the `$end` command.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/naG_hJex8Bs" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```
### Setting a Location

If you announce a raid manually or PokeNav could not identify the gym, you can optionally set the location in one of two ways:

#### If PokeNav knows about your gyms...

Use the `$gym` command to set the location using the name of your gym. Duplicate gym names will present a selection dialog. 

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/NyajO44dVlc" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

#### If you don't have the gym, use the approximate address...

Use the `$address` command to pin and set directions using any address. This will provide a google maps link to users.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/sIq8AD8Eqo0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

### Getting Counters

If the raid boss was set, simply use `$counters` to get the list of counters for that boss. You can also provide current weather conditions, `$counters rain`

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/45tv2WREHZw" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

### Companion Accounts

If you temporarily have friends or family with you that aren't on discord, you can make them in a raid channel by using the `$with` command. The member list and count will reflect the extra non-discord accounts with you.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/fkJkEj5yO9U" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```
