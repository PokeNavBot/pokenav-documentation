# Leaderboards

Leaderboards are **community specific** accomplishments that give your profile a little flare and allow you to show
off for being active in your discord server.

Since leaderboards are community specific, they only show up in your trainer profile when displayed in a guild channel.

This means your profile may look different depending on where the command was run.

## Commands

```eval_rst
.. csv-table:: Interacting with Leaderboards
   :header: "Command", "Who", "Where", "Description"
   :widths: 15, 10, 10, 20

   ``$top``, Anyone, Guild, "Shows the top 10 users in all leaderboards (since last reset)."
   ``$top lifetime``, Anyone, Guild, "Shows the top 10 users in all leaderboards (lifetime)."
   ``$top recent raids-reported 50``, Anyone, Guild, "Shows the top 50 users in all the raids reported leaderboard (since last reset)."
   ``$top lifetime raids-reported 50``, Anyone, Guild, "Shows the top 50 users in all the raids reported leaderboard (lifetime)."
   ``$trainer``, Anyone, Guild, "Shows your leaderboard scores in a guild."
   ``$trainer Dude16``, Anyone, Guild, "Shows Dude16's scores in a guild."
```

## Features


### Profile Medals

If you are in the top 10, a medal will display in your profile under the appropriate statistic. This shows only lifetime scores.

There are special medals for 1st, 2nd and 3rd place:

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/3as9dBDQVvU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

### Top

The top command allows you to see an at a glance view of the top 10 trainers in all leaderboards:

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/cfMz1_O9oMw" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

### Leaderboard Qualifications

To prevent easily manipulating the top 10, some qualification rules exist for each leaderboard:

#### Raid Parties Created

For a raid to count towards `Raid Parties Created`, the following must ALL be true:

* You must be the creator of the raid.
* The raid must end (`$end` or expiration of channel) with at least two people in the raid party.

```eval_rst

.. note:: You do not need to be a member of the raid when it ends.
```

#### Raid Parties Joined

For a raid to count towards `Raid Parties Joined`, the following must ALL be true:

* You must be a member of the raid when it ends.
* The raid must end (`$end` or expiration of channel) with at least two people in the raid party.

```eval_rst

.. note:: You do not need to be the creator of the raid.
```

#### Raids Reported

For a raid to count towards `Raids Reported`, the following must ALL be true:

* You must be the creator of the raid.
* The raid despawn time must have elapsed.
* The raid must have had a valid gym location set, as well as hatch and despawn time.

```eval_rst

.. note:: You do not need to be a member of the raid.
```
