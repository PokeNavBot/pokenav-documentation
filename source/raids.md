# Raiding

## Commands

```eval_rst
.. csv-table:: Announcing and Coordinating Raids
   :header: "Command", "Who", "Where", "Description"
   :widths: 15, 10, 10, 20

   ``$raid latios "St. David's Church" 45``, Anyone, Raid Lobby, "Starts a latios raid at St. David's Church despawning in 45 minutes."
   ``$egg latios "St. David's Church" 45``, Anyone, Raid Lobby, "Starts a latios raid at St. David's Church hatching in 45 minutes."
   ``$exraid "Burpee Park" "July 4th 2018 1:00pm"``, Anyone, EX Raid Lobby, "Starts a mewtwo ex raid party for Burpee Park at 1pm on July 4th."
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
   ``$set-despawn 45``, Creator / Moderator, Raid Party, "Sets the despawn time in minutes."
   ``$set-hatch 45``, Creator / Moderator, Raid Party, "Sets the hatch time in minutes."
   ``$extend 10``, Creator / Moderator, Raid Party, "Extends the channels expiration time by 10 minutes."
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


#### via screenshot

Drop a screenshot of a raid and PokeNav will automatically scan it and create a raid lobby. 

The hatch time, end time and expiration will all be based off the timestamps in the screenshot. 

The boss will be automatically detected using a combination of text recognition and image recognition (even if the bosses name is obscured -- though this will fail if it can't detect the boss and you may need to upload training data so we can refine the image recognition process).

If your servers play area has gyms loaded into PokeNavs database, the location will automatically be set based on the name of the gym and directions will be made available.

### Raid Screenshot Scanning

When uploading screenshots, help PokeNav accurately extract information from the screenshot. Make sure the gym and boss name are visible if possible.

Avoid uploading images before the timer is visible or the boss is zoomed in or not clearly visible -- otherwise you may waste some scan quota.

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

#### $raid command

The `$raid` command with no arguments will create a bare bones channel for coordination. This channel will last for up to 2 hours by default (can be set by server admins).

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/It2L-DTlKSc" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

You can also provide additional details to set information when you first run the command. The first argument is the Pokemon. The second is the exact name of the gym (use quotes if it contains spaces) and the third is the amount of time remaining in minutes. If you use the `$raid` command, it will assume the egg has hatched and the minutes is the despawn time. 

You must set a pokemon to set the gym, you must set a gym to set the time. If it can't find the gym it will default gracefully and still create the channel. If you make a mistake, you can fix the times or gym name by going into the channel and using the appropriate command to correct or set the missing info.

#### $egg command

The `$egg` command exists to indicate that the amount of time specified is the hatch time, not the despawn time, so all timers will be set appropriately for an egg. 

Technically, PokeNav doesn't currently care about eggs, nor do most trainers -- as typically people are looking for certain bosses. If you know the boss (as in when there is a single legendary raid boss), you can use the pokemon's name and it will set the boss right away. Otherwise you can say the egg level `$egg 5 "St. Davids"` and it will leave the boss unset until you manually set it in channel. 

In the future, PokeNav may do something with this raid level, but for now it is simply a placeholder. 

#### $exraid command

The `$exraid` command with no arguments will create a bare bones channel for coordination. This channel will last for up to 14 days by default (can be set by server admins).

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/PCCrBiMa7b0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

You can also provide the gym name and start time of the raid. If you omit the year, PokeNav will assume the current year, so be as detailed as possible. EX raid times cannot be easily corrected with the set-despawn / set-hatch at this time, so it is better to end or re-create the raid or make them via screenshot.

#### via raid roles

Your server admin can designate roles that will automatically trigger a raid channel when used in a message in a raid lobby.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/LkqH6tqvj60" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
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

### Setting the Hatch and Despawn Time

If you created a raid via screenshot, the hatch and despawn are time are set automatically. If you created a raid channel manually and want to provide this information or correct it. You can set those times using the `$set-hatch` and `$set-despawn` commands. 

Using `$set-hatch 30` will set the raid to assume the egg will hatch in 30 minutes and despawn 45 minutes later. The channels expiration time will be extended automatically to accomodate the new time.

Using `$set-despawn 30` will set the raid to assume the boss will despawn in 30 minutes. The hatch time will be set to 0 (45 minutes before the end of the raid). The channel's expiration time will be extended automatically to accomodate the new time.

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
