# Raid Trains
```eval_rst

.. note::
    Raid train support is a new feature.
    
    Please provide feedback if you have some on how it can be improved.
```

## Commands

```eval_rst
.. csv-table:: Announcing and Coordinating Trains
   :header: "Command", "Who", "Where", "Description"
   :widths: 15, 10, 10, 20

   ``$t Horsham Park Train``, Anyone, Raid Lobby, "Starts a raid train channel called `Horsham Park Train`."
   ``$t "Route Name" 4:00 pm``, Anyone, Raid Lobby, "Starts a raid train channel that loads the route and start time provided."
   ``$title New Name Of Train``, Raid Moderator, Raid Train Channel, "Updates the name of the raid train."
   ``$rt all``, Anyone, Raid Train Channel, "Shows all the gyms on the route."
   ``$rt up``, Anyone, Raid Train Channel, "Shows upcoming the gyms on the route."
   ``$rt add Gym Name``, Raid Moderator, Raid Train Channel, "Adds a gym to the end of a raid train."
   ``$rt remove Gym Name``, Raid Moderator, Raid Train Channel, "Removes a gym from a raid train."
   ``$rt move "Gym Name 1" "Game Name 2"``, Raid Moderator, Raid Train Channel, "Moves the first gym to be before the second."
   ``$rt next``, Raid Moderator, Raid Train Channel, "Advances to next gym, resets everyone's arrival status."
   ``$rt save Route Name``, Raid Moderator, Raid Train Channel, "Saves the current train schedule as a new route."
   ``$rt load Route Name``, Raid Moderator, Raid Train Channel, "Clears the schedule and loads the named route as the new schedule."
   ``$rt auto-time``, Raid Moderator, Raid Train Channel, "Toggles automatic times for gyms."
   ``$rt raid-pace 5``, Raid Moderator, Raid Train Channel, "Sets the number of minutes spent for each raid."
   ``$rt travel-pace 40``, Raid Moderator, Raid Train Channel, "Sets the average travel speed (km/h)."
   ``$rt start-time 2:00pm``, Raid Moderator, Raid Train Channel, "Sets the start time for the first gym in the route."
   ``$rt clear``, Raid Moderator, Raid Train Channel, "Clears all gyms from the route."
   ``$list routes``, Anyone, Anywhere, "Shows a list of saved routes owned by your community."
   ``$show route Route Name``, Anyone, Anywhere, "Shows all the locations in the specified route."
   ``$delete route Route Name``, Anyone, Moderation Channel, "Deletes a route from your community."
   ``$toggle raid-trains``, Anyone, Moderation Channel, "Disables the `$train` command in raid lobbies."
   ``$set train-travel-pace 40``, Anyone, Moderation Channel, "Sets the default average travel speed (km/h) for new trains."
   ``$set train-raid-pace 40``, Anyone, Moderation Channel, "Sets the default number of minutes spent for each raid for new trains."

```

## Overview

Often, trainers will form together raiding groups which hit multiple gyms consecutively. While doing this, tracking the progress of the group and reporting raids becomes cumbersome.

Trains are PokeNav's attempt to **improve coordination, visibility and reporting in discord** while these groups are active.

The train feature is designed to help the most with raid hours and events where an optimal route is saved ahead of time. For regular trains it might be easier to create a standard room, as the adminstrative setup effort is higher than a typical raid.

### About Raid Trains

Trains are simply raid coordination channels with special features and limitations. All raid commands are support with a few exceptions (listed below).

Raid trains will **always** create channels in discord, you need to disable the feature if you do not want this.

Keep in mind, instead of keeping accurate information about a singe raid at a single gym, trains focus on tracking lists of gyms and where the group is heading.


#### Added Features

* Channel and role name for the channel is tied to a title for the raid, not the gym.
* Maintain (add or remove) a list of gyms where the group is heading.
* Tracks the current progress of the raid party.
* Advance to the next gym and auto-reset the raid parties arrival status.
* Automatically estimate arrival times and update these times as you go.
* Save the list of gyms as a route, which can then be loaded for future trains.
* View a list or complete gym list of saved community routes.
* Delete community saved routes.
* Default 4 hour duration.
* Gyms marked as EX eligible in the database are marked as such in the schedule.

#### Removed Features

* Raid trains may not set a hatch or despawn time.
* Raid trains do not appear in the PokeNav mobile app or pgmap.org (they are discord only).
* Raid trains can only stop at POI marked as gyms in PokeNav.
* No deduplication of train channels.


### Commands To Learn

Raid coordinators will need to become familiar with the following commands:

`$train` or `$t` will start a train in any raid lobby (see the table).

`$route` or `$rt` (raid train or route shortened) is the top level command to manage a trains routes.

You can run `$help rt` to see the options, or read the table above for an overview.

#### Aliases

There are typically shortened aliases for all the commands to make this easier. Notable aliases:

* `$rt a Gym Name` to add a gym.
* `$rt r Gym Name` to remove a gym.
* `$rt n` to move to the next gym.

### Routes Saving / Re-use

Routes are one of the main value adds for the train feature. Use it during special raid events when you hit a known list of gyms by setting up a train and saving the schedule as a route. You can then re-load the route next raid event for a quick setup.

```eval_rst

.. note::
    At this time, routes are immutable and uniquely named for your community.

    This means that you can only create and delete routes, not modify them. There are no limits to how many routes you can save during the beta. If you need to re-use a name, delete the first route and then save the new route.
```

