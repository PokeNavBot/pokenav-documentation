# Server Settings 

These commands can only be run in the moderation room, which is accessible to server owners and adminstrators.

## Commands

The following commands can **ONLY** be done in the moderation channel, by anyone with permissions to write to that channel.

```eval_rst
.. csv-table:: Managing Your PokeNav Installation
   :header: "Command", "Description"
   :widths: 5, 20

   ``$quickstart``, "Previews quickstart installation of PokeNav."
   ``$quickstart YES``, "Sets up PokeNav installation"
   ``$set-mod-channel #channel``, "Changes the moderation channel."
   ``$set prefix $``, "Changes the prefix used by PokeNav for your server."
   ``$set timezone US/Eastern``, "Sets the timezone localization for this server."
   ``$set location 45.123 -75.123123``, "Sets the center point of a community play area."
   ``$set radius 20``, "Sets the minimum radius of your community (in kilometers)."
   ``$show-settings``, "Shows all your bot configuration settings for this server."
   ``$set-bot-announcement-channel #news``, "Updates where bot announcements are sent (default: moderation channel)."
   ``$set-profile-channel #profile-setup``, "Updates where scans profile images for setting teams."
   ``$toggle 24-hour-time``, "Toggles timestamps as 24-hour time instead of AM/PM."
```

```eval_rst
.. csv-table:: Moderating Teams
   :header: "Command", "Description"
   :widths: 5, 20
   
   ``$set-team-role mystic team-mystic``, "Sets the role used to track a members in-game team."
   ``$toggle auto-assign-team``, "Toggles whether  users will be auto assigned a team role when joining your community."
```

```eval_rst
.. csv-table:: Moderating Trades
   :header: "Command", "Description"
   :widths: 5, 20

   ``$create-active-trades-channel``, "Creates a new channel and publishes all future active trades there."
   ``$enable-trade-lobby #channel``, "Enables trade commands in a channel."
   ``$disable-trade-lobby #channel``, "Disables trade commands in a channel."
   ``$set trade-request-limit 5``, "Sets maximum number of trade requests that can be made by a given user."
   ``$set trade-duration-secs 275000``, "Sets the amount of time before trades expire on your server."
```

```eval_rst
.. csv-table:: Moderating Raids
   :header: "Command", "Description"
   :widths: 5, 20

   ``$disable-ex-raid-lobby #channel``, "Disables EX raid announcements in the channel."
   ``$disable-raid-lobby #channel``, "Disables raid announcements."
   ``$disable-raid-role raid-latios``, "Disables a role used to start raids."
   ``$enable-ex-raid-lobby #channel``, "Enables EX raid announcements in the channel."
   ``$enable-ex-raid-role raid-mewtwo``, "Enables EX raid announcements via raid-mewtwo role."
   ``$enable-raid-lobby #channel``, "Enables raid announcements in the channel."
   ``$enable-raid-role raid-latios``, "Enables raid announcements via raid-latios role."
   ``$create-active-raids-channel``, "Creates a new channel and publishes all future active raids there."
   ``$create-ex-raid-category Category Name``, "Creates a new category where EX raids will be placed."
   ``$set-ex-raid-duration-secs 604800``, "Maximum amount of time an EX raid channel can exist, in seconds."
   ``$create-raid-category Category Name``, "Creates a new category where raids will be placed."
   ``$set-raid-duration-secs 7200``, "Maximum amount of time a raid channel can exist, in seconds."
   ``$set-raid-moderation-role raid-moderator``, "The role that can take privledged actions in raid channels (like ending it)."
   ``$set-raid-viewer-role raid-viewer``, "The role that can view all active raid channels."
   ``$toggle-raid-roles``, "Toggles whether you allow announcing raids via role mentions."
   ``$toggle restrict-status``, "Toggles whether you allow anyone to update the status in a raid."
   ``$toggle auto-insert-counters``, "Toggles whether raid boss counters get automatically inserted in a raid."
   ``$toggle auto-insert-cheatsheet``, "Toggles whether to insert cheatsheet at start of a raid."
   ``$toggle avoid-duplicate-raids``, "Toggles whether to avoid more than a single raid or ex raid at a gym."
   ``$toggle create-raid-channels``, "Toggles whether bot is allowed to create channels for raids."
   ``$toggle create-raid-channel-immediately #raid-lobby``, "Toggles whether raids in this lobby should create a channel immediately or wait until someone joins."
   ``$toggle clean-raid-lobbies``, "Toggles whether raid messages are deleted by the bot."
   ``$toggle public-raid-channels``, "Toggles whether raid channels should be visible to anyone in the raid lobby."
   ``$toggle share-raid-reports``, "Toggles whether raids are reported to the mobile app."
   ``$set-member-shared-quota``, "Sets the number of scans an individual can take from the shared pool."
```

```eval_rst
.. csv-table:: Moderating Badges 
   :header: "Command", "Description"
   :widths: 5, 20

   ``$all-badges``, "Lists all badges and whether are listed as available."
   ``$create-badge :emoji: "Name" "Requirements"``, "Creates a new badge with the given emoji, name and requirements."
   ``$grant-badge 1 Dude16``, "Grants badge #1 to Dude16."
   ``$grant-badge 1 raid-mewtwo-123``, "Grants badge #1 to everyone in the role raid-mewtwo-123."
   ``$revoke-badge 1 Dude16``, "Revokes badge #1 from Dude16."
   ``$revoke-badge 1 raid-mewtwo-123``, "Revokes badge #1 from everyone in the role raid-mewtwo-123."
   ``$toggle-badge 1``, "Toggles whether badge #1 appears in the `$available-badges` list."
   ``$update-badge 1 :emoji: "Name" "Requirements"``, "Updates badge #1 with new emoji, name and requirements."
   ``$badge-report 1``, "Shows a report showing recent recipients and up to 150 trainers who earned the badge."
   ``$set-badge-channel #trophy-room``, "Badges will be awarded will be announced in #trophy-room."

```

## Features

```eval_rst

.. note::
    
    Complete documentation coming shortly...
```

### Community Management

#### Raid Channels

By default, PokeNav creates a channel for every raid that is announced, when it is announced. 

If you want to turn this off raid channels on your server, use `$toggle create-raid-channels`.

If you want to wait until someone joins a raid to make a channel, you can toggle this per raid lobby / callout channel: `$toggle create-raid-channels-immediately #raid-lobby`

##### Why would you want to make channels immediately? 

If you make a channel immediately, then when a user posts a screenshot they can be automatically added to it. This is useful for level 5 and 4 raids. It also gives you flexibility to run your server the way you like.

##### Why would you not want to make channels immediately? 

PokeNav uses a channel and role to coordinate raids. This is a limited discord resource, so you may want to report many raids but delay creating channels until people need them, avoiding using a role unless it is necessary.


#### Scanning Team Images 

Disabled by default, you can set a profile channel. When this is set, users can upload a screenshot of their in-game profile and PokeNav will set their team and role based according to what it believes their team to be. Team scans don't count against your quota.

<img src="/_static/imgs/team_scan.png" />

```eval_rst

.. note::
    
    To prevent accidently changing teams, PokeNav will only assign your team if you do not have a team role assigned on that server. You can change your team with the `$team` command.
```

#### Auto Assign Team Roles

Disabled by default, you can allow PokeNav to automatically assign members a team role if they already configured their team on another server. 

When a user joins your server, if you have this setting enabled, they will automatically be added to the proper team role if one is set for your server.


```eval_rst

.. warning::
    
    This is disabled by default because doing so may allow malicious users to circumvent discord verification levels.

    Be sure you have a good spam / moderation bot in your server before you enable this setting.
```

#### Gym and Pokestop Awareness

PokeNav sources gym and pokestop locations from user submitted datasets and other known sources. If you configure a location and radius for your server, you can gain access to search those gyms and pokestops as well as automatically match directions when you submit raid screenshots.

`$set-location lat lon` will set a server with a default radius as the "play area" for your server. PokeNav will include any gyms and pokestops that fall into the play area when looking up directions. If you need to adjust your radius, use `$set-radius`. Play area with a radius up to 100km is currently supported.


### Badges

You can create badges from custom server emoji and award them to members for achieving certain goals. Everything is done by moderator discretion, so make badges for whatever you like. At the moment, if you delete the emoji for a badge its image will be removed from every trainers badge list (so please keep those around).

Most badge operations work by referencing a badges unique id. When you create a badge, PokeNav will generate a unique id and display it alongside the badge when it is displayed. This id is also used to grant and revoke badges, as well as update its description.

#### Creating Badges

To create a badge, use the `$create-badge` command. A badge requires a custom emoji owned by your server, a unique name (unique to the server it exists under) and a requirements description. 

You must quote the name and requirements to capture it properly. Names are limited to 80 characters and requirements to 256. Emoji can be animted and it actually makes the badge that much cooler.

Its recommended to make the requirements brief and describe what needs to be done to obtain it, as well as reference a channel where more information might be obtained.


```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/zcHGNHI5HpE" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

#### Updating Badges

If you need to update a badges emoji, name or requirements you can use the `$update-badge` command, which works EXACTLY like `$create-badge` but takes the badge id as the first item and updates that badge instead of creating a new one:


```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/MX3mVot12m4" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

#### Hiding Badges

Sometimes you don't want badges to be visible or you want to retire them. `$toggle-badge` will hide it from the `$available-badges` list. You can still grant and change it, but it won't be visible to non-mods.

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/dgFuMmwB-L4" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

#### List All Badges

In addition to `$available-badges`, mods have access to `$all-badges` which also shows unavailable badges if they've been toggled off.

#### Setting a Badge Announcement Channel

When you grant a badge, you can have the award be pubicly announced in the badge announcement channel. This will be created for you by `$quickstart`, but if you need to set it you can use the `$set-badge-channel` command:

`$set-badge-channel #trophy-room`

#### Granting Badges

To grant a user a badge, use `$grant-badge` and provide the badge id and the name of the user. Like all commands the name can either be the user nickname or their full discord name with discriminator:

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/FCj8nA4pr90" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

#### Revoking Badges

If you need to take back a badge, use `$revoke-badge` that same way you used `$grant-badge`. It won't be announced but the badge will disappear from the users profile. You can use `$grant-badge` to give the user the badge back:

```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/WCUef2YFrDg" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```
