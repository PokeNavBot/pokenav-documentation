# Admin's Guide

PokeNav has many features, which you as the admin have the ability to leverage and enabled.

All of the following features are utlitized using commands run inside the `#pokenav` channel. 

## Server Settings

### Commands

```eval_rst
.. csv-table:: Managing Your PokeNav Installation
   :header: "Command", "Description"
   :widths: 5, 20

   ``$quickstart``, "Previews quickstart installation of PokeNav."
   ``$quickstart YES``, "Sets up PokeNav installation"
   ``$set mod-channel #channel``, "Changes the moderation channel."
   ``$set prefix $``, "Changes the prefix used by PokeNav for your server."
   ``$set timezone US/Eastern``, "Sets the timezone localization for this server."
   ``$set location 45.123 -75.123123``, "Sets the center point of a community play area."
   ``$set radius 20``, "Sets the minimum radius of your community (in kilometers)."
   ``$show settings``, "Shows all your bot configuration settings for this server."
   ``$report quota``, "Shows a quota report, along with a top contributors list."
   ``$set bot-announcement-channel #news``, "Updates where bot announcements are sent (default: moderation channel)."
   ``$set profile-channel #profile-setup``, "Updates where scans profile images for setting teams."
   ``$toggle 24-hour-time``, "Toggles timestamps as 24-hour time instead of AM/PM."
   ``$toggle share-invite-url``, "Toggles sharing a public invite for your server."
   ``$toggle third-party-access``, "Toggles sharing report data with third party developers."
   ``$reset-leaderboard raids-reported``, "Resets everyone's Raids Reported leaderboard scores (recent only)."
```

### Guide

#### Third Party Access

PokeNav provides some open APIs and public datasets that can be used by the larger Pokemon Go community to create tools and infographics. By default, all communities are opt-in to sharing with third party developers. You can use the `$toggle third-party-access` command to disable / enable future reports.

Third Parties never gain access to personal information such as which trainer reported the raid, status information or members attending. They can see at most, the location of the raid, its start or end time and the community which reported it.

#### Creating Badges

## Badges

### Commands

```eval_rst
.. csv-table:: Moderating Badges 
   :header: "Command", "Description"
   :widths: 5, 20

   ``$all-badges``, "Lists all badges and whether are listed as available."
   ``$create badge :emoji: "Name" "Requirements"``, "Creates a new badge with the given emoji, name and requirements."
   ``$update badge 1 :emoji: "Name" "Requirements"``, "Updates badge #1 with new emoji, name and requirements."
   ``$grant-badge 1 Dude16``, "Grants badge #1 to Dude16."
   ``$grant-badge 1 raid-mewtwo-123``, "Grants badge #1 to everyone in the role raid-mewtwo-123."
   ``$revoke-badge 1 Dude16``, "Revokes badge #1 from Dude16."
   ``$revoke-badge 1 raid-mewtwo-123``, "Revokes badge #1 from everyone in the role raid-mewtwo-123."
   ``$toggle-badge 1``, "Toggles whether badge #1 appears in the `$available-badges` list."
   ``$report badge 1``, "Shows a report showing recent recipients and up to 150 trainers who earned the badge."
   ``$set badge-channel #trophy-room``, "Badges will be awarded will be announced in #trophy-room."

```

### Guide

You can create badges from custom server emoji and award them to members for achieving certain goals. Everything is done by moderator discretion, so make badges for whatever you like. At the moment, if you delete the emoji for a badge its image will be removed from every trainers badge list (so please keep those around).

Most badge operations work by referencing a badges unique id. When you create a badge, PokeNav will generate a unique id and display it alongside the badge when it is displayed. This id is also used to grant and revoke badges, as well as update its description.

#### Creating Badges

To create a badge, use the `$create badge` command. A badge requires a custom emoji owned by your server (or by a server PokeNav is in and you can reference it with discord nitro), a unique name (unique to your server) and a requirements description. 

You must quote the name and requirements to capture it properly. Names are limited to 80 characters and requirements to 256. Emoji can be animated and it actually makes the badge that much cooler.

It's recommended to make the requirements brief and describe what needs to be done to obtain it, as well as reference a channel where more information might be obtained.

If you used an emoji from another server and that server gets rid of PokeNav, PokeNav may lose the ability to post that emoji, but the badge image will be preserved. 


```eval_rst
.. raw:: html

    <div class="video-container">
    <iframe src="https://www.youtube.com/embed/zcHGNHI5HpE" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
```

#### Updating Badges

If you need to update a badges emoji, name or requirements you can use the `$update-badge` command, which works EXACTLY like `$create badge` but takes the badge id as the first item and updates that badge instead of creating a new one:


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

When you grant a badge, you can have the award be pubicly announced in the badge announcement channel. This will be created for you by `$quickstart`, but if you need to set it you can use the `$set badge-channel` command:

`$set badge-channel #trophy-room`

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


## Teams

### Commands

```eval_rst
.. csv-table:: Moderating Teams
   :header: "Command", "Description"
   :widths: 5, 20
   
   ``$set team-role mystic team-mystic``, "Sets the role used to track a members in-game team."
   ``$toggle auto-assign-team``, "Toggles whether  users will be auto assigned a team role when joining your community."
   ``$toggle restrict-team-screenshots``, "Toggles reading screenshots when a team role is set."
   ``$toggle team-command``, "Toggles the team command in your server."
```

### Guide

#### Scanning Team Images 

Disabled by default, you can set a profile channel. When this is set, users can upload a screenshot of their in-game profile and PokeNav will set their team and role based according to what it believes their team to be. Team scans don't count against your quota.

<img src="/_static/imgs/team_scan.png" />

```eval_rst

.. note::
    
    To prevent accidently changing teams, PokeNav will only assign your team if you do not have a team role assigned on that server. You can change your team with the `$team` command. You can use the settings below to override this, but we don't recommend changing it unless you are sure!
```

#### Restrict Team Screenshots

By default, PokeNav will only read team screenshots if the user didn't have a team role set (preventing the user from switching teams).

You can allow them to switch teams, even if they already had one, by toggling this feature OFF.

#### Auto Assign Team Roles

Disabled by default, you can allow PokeNav to automatically assign members a team role if they already configured their team on another server. 

When a user joins your server, if you have this setting enabled, they will automatically be added to the proper team role if one is set for your server.


```eval_rst

.. warning::
    
    This is disabled by default because doing so may allow malicious users to circumvent discord verification levels.

    Be sure you have a good spam / moderation bot in your server before you enable this setting.
```

## Raiding

### Commands

```eval_rst
.. csv-table:: Moderating Raids
   :header: "Command", "Description"
   :widths: 5, 20

   ``$toggle ex-raid-lobby #channel``, "Enable / disables EX raid announcements."
   ``$toggle raid-lobby #channel``, "Enable / disables raid announcements."
   ``$create active-raids-channel``, "Creates a new channel and publishes all future active raids there."
   ``$create active-ex-raids-channel``, "Creates a new channel and publishes all future active EX raids there."
   ``$create-ex-raid-category Category Name``, "Creates a new category where EX raids will be placed."
   ``$create-raid-category Category Name``, "Creates a new category where raids will be placed."
   ``$set raid-moderation-role raid-moderator``, "The role that can take privledged actions in raid channels (like ending it)."
   ``$set raid-viewer-role raid-viewer``, "The role that can view all active raid channels."
   ``$toggle restrict-status``, "Toggles whether you allow anyone to update the status in a raid."
   ``$toggle auto-insert-counters``, "Toggles whether raid boss counters get automatically inserted in a raid."
   ``$toggle auto-insert-cheatsheet``, "Toggles whether to insert cheatsheet at start of a raid."
   ``$toggle avoid-duplicate-raids``, "Toggles whether to avoid more than a single raid or ex raid at a gym."
   ``$toggle create-raid-channels``, "Toggles whether bot is allowed to create channels for raids."
   ``$toggle create-raid-channel-immediately #raid-lobby``, "Toggles whether raids in this lobby should create a channel immediately or wait until someone joins."
   ``$toggle clean-raid-lobbies``, "Toggles whether raid messages are deleted by the bot."
   ``$toggle public-raid-channels``, "Toggles whether raid channels should be visible to anyone in the raid lobby."
   ``$toggle share-raid-reports``, "Toggles whether server (and its raids) are reported to the mobile app."
   ``$toggle tag-egg-on-hatch``, "Toggles whether the raid party should be tagged on hatch."
   ``$toggle allow-bot-screenshots``, "Toggles whether PokeNav reads screenshots from other bots."
   ``$set member-shared-quota 50``, "Sets the number of scans an individual can take from the shared pool."
   ``$set assumed-t5 mewtwo``, "Assumes all tier 5 eggs are Mewtwo."
```

### Guide

#### Raid Channel Settings

By default, PokeNav creates a channel for every raid that is announced, when it is announced. 

If you want to turn this off raid channels on your server, use `$toggle create-raid-channels`.

If you want to wait until someone joins a raid to make a channel, you can toggle this per raid lobby / callout channel: `$toggle create-raid-channels-immediately #raid-lobby`

##### Why would you want to make channels immediately? 

If you make a channel immediately, then when a user posts a screenshot they can be automatically added to it. This is useful for level 5 and 4 raids. It also gives you flexibility to run your server the way you like.

##### Why would you not want to make channels immediately? 

PokeNav uses a channel and role to coordinate raids. This is a limited discord resource, so you may want to report many raids but delay creating channels until people need them, avoiding using a role unless it is necessary.


## Research

### Commands

```eval_rst
.. csv-table:: Moderating Research
   :header: "Command", "Description"
   :widths: 5, 20

   ``$toggle research-lobby #channel``, "Enable / disables research announcements and screenshots."
   ``$create active-research-channel``, "Creates a new channel and publishes all future research there."
   ``$toggle clean-research-lobbies``, "Enable / disables deletion of screenshots and commands in all research lobbies."
   ``$toggle interactive-research-report``, "Enable / disables prompting for research when a pokestop screenshot is posted."
   ``$delete all-research``, "Clears all current server research reports for the day, such as when an event occurs."
   ``$set research-moderation-role research-moderator``, "The role that can take privledged actions on research (like editing, deleting)."
```

### Guide

#### Research Reports

You can report research using screenshots or commands. Setting up a research lobby is how you control whether your server allows research reporting through PokeNav.

## POI

### Commands

```eval_rst
.. csv-table:: Moderating POI
   :header: "Command", "Description"
   :widths: 5, 20

   ``$create poi gym "Gym Name" 45.00 -75.00``, "Creates a gym at the given lat, lon."
   ``$create poi pokestop "Pokestop Name" 45.00 -75.00``, "Creates a pokestop at the give lat, lon."
   ``$update poi 12345 "name: New Name"``, "Updates POI #12345 with a new name."
   ``$update poi 12345 "type: gym"``, "Updates POI #12345 and sets its type to be gym."
   ``$delete poi 12345``, "Removes POI #12345 from your community."
   ``$poi``, "Shows a detailed POI summary for your server."
   ``$create poi-alias 12345 church``, "Creates a shortcut alias for poi #12345 called church."
   ``$delete poi-alias church``, "Removes the POI alias, church, from your server."
```

### Guide

#### What Are POI?

POI, or Points of Interest, are in-game locations, stored in PokeNav's database, which can be used to enable all sorts of useful features, including raid deduplication, directions, app visibility and more. 

PokeNav has a large, but not complete, database of Point of Interest. We rely on users to upload and add new POI as they become available. 

#### How POI Works In PokeNav

PokeNav contains a database of POI which consists of the POI's name, type, latitude and longitude. It also has other metadata, described later.

PokeNav's POI system was re-written in October 2018 to give server admins complete control over their own server's POI. You can think of your POI database as consisting of two parts: user submitted POI and "verified" POI. Verified POI are gyms and pokestops shared by all PokeNav servers, covering some of the most populated places. PokeNav contains over 2 million verified POI. User submitted POI are those which admins have uploaded to PokeNav and which can only be seen in the server in which they were created.

To use POI you must `$set location` for your server and adjust `$set radius` to an appropriate setting. When a POI lookup is done on your server, PokeNav filters the POI by the play area set and typically looks up the best match, if any.

#### POI Aliases

You can create an "alias" for a POI. This is an alternate name that is used as a fallback for looking up the POI when no other match is found. This is useful for specifying local nick names for popular gyms or shortening the name of a gym to one word so it doesn't require quotes. Aliases must be unique per server (for example, you cannot have two aliases called "church"). Aliases only act as fallback names, they never take priority over full names. You can use an alias any where you use a name of a gym or pokestop.

#### Adding A New Gym / Pokestop

Do the following when a gym or pokestop is missing from your community (either because it was recently added or your community is new):

`$create poi gym "Name Of Gym" 45.00 -75.00`

`$create poi pokestop "Name Of Pokestop" 45.00 -75.00`

#### Figuring Out The Right Coordinates

All coordinates provided must be valid locations inside your community play areas; latitude must be between -90 and 90 and longitude between -180 and 180. 

Remember that the coordinates don't need to be "exact" but should be accurate enough that if someone clicks directions, it takes them to the right place -- at least within visible range of the stop. 

If the pokestop or gym is non-sponsored, you can use the ingress intel map to get a link to the portal. You will need to sign up for an ingress account, but if you click on a portal then press the "link" button in the upper right hand corner you can get a direct link to any portal. For example:

`https://www.ingress.com/intel?ll=40.207983,-75.177594&z=17&pll=40.207319,-75.177512`

The coordinates after `pll` are the POIs actual location. So to create that POI you would do:

`$create poi gym "Deep Meadow Park" 40.207319 -75.177512`

Though, we recommend you making sure that the POI is not actually in the database first. Copy and paste the portal name into `$gi` or `$si` to make sure!

If a POI is sponsored, it won't be on the intel map. Instead go to Google Maps to find the business and drop a pin (press and hold) which will give you coordinates. 

#### Converting a Pokestop To A Gym

First, lookup the existing Pokestop using `$si name of pokestop`. If its "verified" or doesn't exist you need to add a new gym with the same name to your community:

`$create poi gym "Name Of Gym" 45.00 -75.00`

If the pokestop was "unverified", you can simply update it. Lookup the pokestop like above and note the id number in the footer. Then:

`$update poi 12345 "type: gym"`

#### A New Sponsored or EX Eligible Gym / Pokestop

`$create poi gym "Name Of Gym" 45.00 -75.00 "sponsored: 1" "ex_eligible: 1"`

It will show both the "sponsored" and "ex_eligible" tag at the bottom of the bot response.

If you forgot to add a sponsored flag:

`$update poi 12345 "sponsored: 1"

If you accidently made it sponsored

`$update poi 12345 "sponsored: 0"`

#### What POI can I see in my server?

You can see all your community submitted POI and shared verified POI when you search for gyms and pokestops, unless the POI you are looking for shares a name with a verified POI.

POI you upload always "shadow" verified POI of the same type.  Allowing you to update your server's POI without verification. 

For example, let's say that theres a verified POI called "Starbucks" which changed location. You cannot change a verified POI. Instead you can add "Starbucks" with the right location to your server. Going forward, when users try to use "Starbucks" in your server, they will only be able to see "Starbucks" you added. This allows you to customize your server's available POI by eliminating duplicates in the shared set (thereby setting a default) or to update gyms so your server is more current. 

On the other hand if you add a "Starbucks" gym to your set, the "Starbucks" pokestops will still be visible from the verified set and vice versa. 

#### What Restrictions Are There On POI?

Your server cannot have multiple POI with the same name, type and location. 

You can create a POI with the same name and type, but PokeNav won't be able to find it without assistance.

There is a soft limit to how many POI your community can upload, we will adjust and clarify this when file upload becomes available.

#### How Do I Get My POI Verified?

We're still working on the verification system, check in later for more information!


## Notifications

### Commands

```eval_rst
.. csv-table:: Moderating Notifications
   :header: "Command", "Description"
   :widths: 5, 20

   ``$set notification-channel #channel-name``, "Set a dedicated channel for notifications"
   ``$create role role-name``, "Creates a mentionable role"
   ``$create notify-rule role-name "gym: Gym Name"``, "Mentions `role-name` when any raid occurs at the gym"
   ``$create notify-rule role-name "tier: 5" "gym: Gym Name"``, "Mentions `role-name` when a tier 5 raid occurs at the gym"
   ``$create notify-rule role-name "boss: jynx" "gym: Gym Name"``, "Mentions `role-name` when a jynx raid occurs at the gym"
   ``$delete notify-rule 123``, "Deletes the notification role #123"
   ``$delete notify-rule role-name``, "Deletes all rules for `role-name`"
   ``$subs``, "Shows all subscriptions on your server, along with rules"
   ``$subs role-name``, "Shows all roles for the role, if any exist"
   ``$sub role-name``, "Subscribes the user to that role"
   ``$unsub role-name``, "Unsubscribes the user from that role"
```

### Guide

You can configure PokeNav to automatically tag roles when certain raid conditions are met, for example, when a tier 5 raid occurs at one of several EX gyms, or when a Jynx raid is called out. You do this by defining "notify rules", which are checked when someone announced a raid on your server.

You can have up to 25 roles checked for notifications and 15 rules per role (at the time of this writing). You can specify multiple rules per role, and if any of them are true, the role will be mentioned.

If the raid changes to match a rule, like when a boss is updated -- it will issue a follow up notification in the raid lobby or notification channel. Only the newly qualified role will be mentioned. A single raid will never tag the same role more than once.

##### Example: EX Raid Notifications

If say you have three EX gyms in your area, and you want to notify an ex-eligible role whenever a tier 5 is announced, you would run the following commands

`$create notify-rule ex-eligible "tier: 5" "gym: Gym 1"`
`$create notify-rule ex-eligible "tier: 5" "gym: Gym 2"`
`$create notify-rule ex-eligible "tier: 5" "gym: Gym 3"`
`$create notify-rule ex-eligible "tier: 5" "region: 45.0, -75.0, 15"`


##### Example: PokeDraft

Say you are running a PokeDraft and this weeks boss is Jynx:

`$create notify-rule poke-draft-raid-boss "boss: Jynx"`

Users can then subscribe to that role with `$sub poke-draft-raid-boss`. When a Jynx is called out or a tier 3 egg gets update to Jynx, a notification will be sent.

When the boss rotates to a new PokeDraft boss, say Alakazam; you can clear the role:

`$delete notify-rule poke-draft-raid-boss`
`$create notify-rule poke-draft-raid-boss "boss: Alakazam"`


## Trading

### Commands 

```eval_rst
.. csv-table:: Moderating Trades
   :header: "Command", "Description"
   :widths: 5, 20

   ``$create active-trades-channel``, "Creates a new channel and publishes all future active trades there."
   ``$toggle trade-lobby #channel``, "Enable / disable trade commands in a channel."
   ``$set trade-request-limit 5``, "Sets maximum number of trade requests that can be made by a given user."
   ``$set trade-duration-secs 275000``, "Sets the amount of time before trades expire on your server."
```

