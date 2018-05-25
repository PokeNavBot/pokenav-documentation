# Moderation 

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
   ``$set-prefix $``, "Changes the prefix used by PokeNav for your server."
   ``$set-timezone US/Eastern``, "Sets the timezone localization for this server."
   ``$set-location 45.123 -75.123123``, "Sets the center point of a community play area."
   ``$set-radius 20``, "Sets the minimum radius of your community (in kilometers)."
   ``$show-settings``, "Shows all your bot configuration settings for this server."
```

```eval_rst
.. csv-table:: Moderating Teams
   :header: "Command", "Description"
   :widths: 5, 20
   
   ``$set-team-role mystic team-mystic``, "Sets the role used to track a members in-game team."
   ``$toggle-auto-assign-team``, "Toggles whether  users will be auto assigned a team role when joining your community."
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
   ``$set-active-raids-channel #channel``, "Publishes all active raids in this channel."
   ``$set-ex-raid-category Category Name``, "Creates a new category where EX raids will be placed."
   ``$set-ex-raid-duration-secs 604800``, "Maximum amount of time an EX raid channel can exist, in seconds."
   ``$set-raid-category Category Name``, "Creates a new category where raids will be placed."
   ``$set-raid-duration-secs 7200``, "Maximum amount of time a raid channel can exist, in seconds."
   ``$set-raid-moderation-role raid-moderator``, "The role that can take privledged actions in raid channels (like ending it)."
   ``$set-raid-viewer-role raid-viewer``, "The role that can view all active raid channels."
   ``$toggle-raid-roles``, "Toggles whether you allow announcing raids via role mentions."
   ``$toggle-restrict-status``, "Toggles whether you allow anyone to update the status in a raid."
```

```eval_rst
.. csv-table:: Moderating Badges 
   :header: "Command", "Description"
   :widths: 5, 20

   ``$all-badges``, "Lists all badges and whether are listed as available."
   ``$create-badge :emoji: "Name" "Requirements"``, "Creates a new badge with the given emoji, name and requirements."
   ``$grant-badge 1 Dude16``, "Grants badge #1 to Dude16."
   ``$revoke-badge 1 Dude16``, "Revokes badge #1 from Dude16."
   ``$toggle-badge 1``, "Toggles whether badge #1 appears in the `$available-badges` list."
   ``$update-badge 1 :emoji: "Name" "Requirements"``, "Updates badge #1 with new emoji, name and requirements."

```

## Features

```eval_rst

.. note::
    
    Complete documentation coming shortly...
```

### Community Management

#### Auto Assign Team Roles

Disabled by default, you can allow PokeNav to automatically assign members a team role if they already configured their team on another server. 

When a user joins your server, if you have this setting enabled, they will automatically be added to the proper team role if one is set for your server.


```eval_rst

.. warning::
    
    This is disabled by default because doing so may allow malicious users to circumvent discord verification levels.

    Be sure you have a good spam / moderation bot in your server before you enable this setting.
```

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
