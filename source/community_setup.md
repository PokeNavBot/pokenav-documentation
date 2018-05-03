# Community Setup

## Purpose

This guide exists to help discord server owners setup PokeNav in their community.

## Trying It Out

If you want to test out PokeNav from a user's perspective, you can do so on the [PokeNav Discord Server](https://discord.gg/7M9quNd). The production bot is setup for users to interact with by posting raids, setting up their trainer profile and any other feature currently supported (except for moderation commands).

## Inviting PokeNav 

To get an invite link to PokeNav, please visit the PokeNav Discord Server and request beta access.

Once PokeNav is added to your server, it will immediately create a new channel called `#pokenav`. This is the moderation channel, it can be changed at any time, but a moderation channel must always exist. If you delete the moderation channel, PokeNav will attempt to recreate one within a few minutes. You must be an adminstrator or server owner to see #pokenav.

## Configuring PokeNav

PokeNav can be configured to suit most communities.

How you go about doing it depends on whether you have an existing community with certain raid organization preferences or are starting fresh.

### Quickstart 

PokeNav comes with a moderation command called `$quickstart` which is designed to get new communities up and running in a under a minute. Here's how it works:

In your moderation channel (#pokenav), type `$quickstart`. 

Don't worry, nothing will happen. PokeNav will instead show you a summary of what it will do:

![quickstart preview](_static/imgs/preview_quickstart.png)

Let's go through what this means. 

PokeNav will do a bunch of things for you if you type `$quickstart YES`. These can be changed, renamed or removed at any time. Lets go through each:

<dl>
<dt>Active Raids Channel (#active-raids)</dt>
<dd>A single channel where all raids in your server appear, no one but PokeNav can post here. Gives trainers a clutter-free view of every raid and the option to join any raid.</dd>

<dt>Raid Lobby / EX Raid Lobby (#announce-raids-here)</dt>
<dd>A single channel where users can post new raids. Commands to start raids will be ignored anywhere but in this channel.</dd>

<dt>Raid Party Category (Raid Parties)</dt>
<dd>Channels created to coordinate each raid will be placed under this category. If deleted, will place channels next to the Raid Lobby it where it was announced.</dd>

<dt>Raid Viewer Role (@raid-viewer)</dt>
<dd>Users in this role will be able to read and write in all active raid channels, even if they are not apart of the raid party. In PokeNav, raid parties are invisible to everyone but Raid Viewers and Raid Party Members.</dd>

<dt>Raid Moderator Role (@raid-moderator)</dt>
<dd>Users in this role will be able to perform privledged actions in raids. This includes ending the raid early, updating the public status or reseting the raid parties arrival status.</dd>

<dt>Team Roles (mystic, instinct, valor)</dt>
<dd>PokeNav will attempt to automatically detect your team roles, or create them if they don't exist. Roles with the words `mystic`, `instinct` or `valor` will be detected automatically.</dd>
</dl>

Don't worry if everything isn't exactly the way you want it. You can immediatelly rename or delete any channel or role created by `$quickstart`.

Once you run `$quickstart YES` you will have a fully functioning PokeNav installation.

### Recommendations: Integrating Into An Existing Community

Using `$quickstart` described above can be valuable even if you don't want the exact setup it provides, since it will save you several steps (creating roles and setting team roles manually). There are commands to do everything done in `$quickstart` so see the moderation commands section for details.

#### Multiple Raid Lobby Channels

A common configuration is a server for a large area where each channel represent a town or neighborhood of gyms. PokeNav can handle an arbitrary number of raid lobby channels, simply run the following command in your moderation channel for each one you want to enable:

`$enable-raid-lobby #channel-name`

If you also want to allow EX raid announcements, run:

`$enable-ex-raid-lobby #channel-name`

You can disable a raid lobby by deleting the channel, or by running:

`$disable-raid-lobby #channel-name`

You can disable an ex raid lobby by deleting the channel, or by running:

`$disable-ex-raid-lobby #channel-name`

### Post Install

#### Setup Your Mods

Once PokeNav is configured, add all your mods and admins to `raid-moderators` so they have permissions to end and mentor other trainers in using the bot. It will allow them to take any action the creator of the raid could take.
