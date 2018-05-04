# Moderation 

These commands can only be run in the moderation room, which is accessible to server owners and adminstrators.

## Commands

```eval_rst
.. csv-table:: Managing Your PokeNav Installation
   :header: "Command", "Who", "Where", "Description"
   :widths: 15, 10, 10, 20

   ``$disable-ex-raid-lobby #channel``, Anyone, Mod Channel, "Disables EX raid announcements in the channel."
   ``$disable-raid-lobby #channel``, Anyone, Mod Channel, "Disables raid announcements."
   ``$disable-raid-role raid-latios``, Anyone, Mod Channel, "Disables a role used to start raids."
   ``$enable-ex-raid-lobby #channel``, Anyone, Mod Channel, "Enables EX raid announcements in the channel."
   ``$enable-ex-raid-role raid-mewtwo``, Anyone, Mod Channel, "Enables EX raid announcements via raid-mewtwo role."
   ``$enable-raid-lobby #channel``, Anyone, Mod Channel, "Enables raid announcements in the channel."
   ``$enable-raid-role raid-latios``, Anyone, Mod Channel, "Enables raid announcements via raid-latios role."
   ``$quickstart``, Anyone, Mod Channel, "Previews quickstart installation of PokeNav."
   ``$quickstart YES``, Anyone, Mod Channel, "Sets up PokeNav installation"
   ``$set-active-raids-channel #channel``, Anyone, Mod Channel, "Publishes all active raids in this channel."
   ``$set-ex-raid-category Category Name``, Anyone, Mod Channel, "Creates a new category where EX raids will be placed."
   ``$set-ex-raid-duration-secs 604800``, Anyone, Mod Channel, "Maximum amount of time an EX raid channel can exist, in seconds."
   ``$set-mod-channel #channel``, Anyone, Mod Channel, "Changes the moderation channel."
   ``$set-prefix $``, Anyone, Mod Channel, "Changes the prefix used by PokeNav for your server."
   ``$set-raid-category Category Name``, Anyone, Mod Channel, "Creates a new category where raids will be placed."
   ``$set-raid-duration-secs 7200``, Anyone, Mod Channel, "Maximum amount of time a raid channel can exist, in seconds."
   ``$set-raid-moderation-role raid-moderator``, Anyone, Mod Channel, "The role that can take privledged actions in raid channels (like ending it)."
   ``$set-raid-viewer-role raid-viewer``, Anyone, Mod Channel, "The role that can view all active raid channels."
   ``$set-team-role mystic team-mystic``, Anyone, Mod Channel, "Sets the role used to track a members in-game team."
   ``$set-timezone US/Eastern``, Anyone, Mod Channel, "Sets the timezone localization for this server."
   ``$show-settings``, Anyone, Mod Channel, "Shows all your bot configuration settings for this server."
   ``$toggle-auto-assign-team``, Anyone, Mod Channel, "Toggles whether  users will be auto assigned a team role when joining your community."
   ``$toggle-raid-roles``, Anyone, Mod Channel, "Toggles whether you allow announcing raids via role mentions."
   ``$toggle-restrict-status``, Anyone, Mod Channel, "Toggles whether you allow anyone to update the status in a raid."

```

## Features

```eval_rst

.. note::
    
    Complete documentation coming shortly...
```

### Raid Lobby

### EX Raid Lobby

### Auto Assign Team Roles

Disabled by default, you can allow PokeNav to automatically assign members a team role if they already configured their team on another server. 

When a user joins your server, if you have this setting enabled, they will automatically be added to the proper team role if one is set for your server.


```eval_rst

.. warning::
    
    This is disabled by default because doing so may allow malicious users to circumvent discord verification levels.

    Be sure you have a good spam / moderation bot in your server before you enable this setting.
```
