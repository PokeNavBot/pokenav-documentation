# Research

## Commands

```eval_rst
.. csv-table:: Announcing and Coordinating Raids
   :header: "Command", "Who", "Where", "Description"
   :widths: 15, 10, 10, 20

   ``$q misdreavus "Township park"``, Anyone, Research Lobby, "Reports a misdreavus reward quest."
   ``$q misdreavus "Township park" "Transfer 10 Pokemon"``, Anyone, Research Lobby, "Reports a misdreavus reward quest, with task text."
   ``$q "rare candy" "Township park"``, Anyone, Research Lobby, "Reports a rare candy reward quest."
   ``$list q``, Anyone, Research Lobby, "Lists all quests / research in the server, grouped by research reward."
   ``$list q #channel-name``, Anyone, Research Lobby, "Lists all quests / research in the channel specified."

```

## Terminology

#### Research Lobby

A channel that the discord server moderators have enabled to allow for research reports. Research commands are not allowed in a channel unless expicilty enabled by making it a research lobby, allowing you to ignore PokeNav's research report features, if you so choose.


## Features

### Philosophy

Research is not as self-contained as raids. There is no screenshot you can post that contains all the information required to identify and locate a research task. Instead, we settled on a workflow that focuses on what people want: the reward.

Two things are required to report a research task -- the reward and the pokestop. The task description is optional. You can specify anything in the reward text, but using  `Unknown`, `u` or `?` as the reward will display the reward as "???".

### Reporting Research

With PokeNav, reporting research is easy.

#### via command

`$q misdreavus "pokestop name" "task description"`

Will report a misdreavus quest at the Pokestop you specified. If you the

#### via screenshot

Drop a screenshot of a pokestop along with the research and/or task description (in the same message) and PokeNav will automatically scan it and create a report, saving you the trouble of typing the often long pokestop name.

If you don't include text with the image, PokeNav will prompt you for the research reward / task. This behavior can be adjusted by your admins. If an image is skipped, because you didn't provide reward, it will not count against quota.

Using a screenshot makes reporting the research easier because you don't need quotes, instead separate it by comma:

`Misdreavus, Transfer 10 Pokemon`

or for just the reward:

`Misdreavus`

### Reward Images

If the reward item is in the database and properly identified, it will display either as the name of the item or the name of a Pokemon Encounter. In the case of Pokemon, the image will be displayed. For select items, artwork will be displayed (i.e. stardust, rare candy, pokeballs, berries). If the item is not recognized or artwork is unavailable, a placeholder will be shown.

### Localization

Research is the first feature where we are testing dynamic, server based language localization. The research reward input can be localized such that input in your local language will show proper artwork.

Output is not yet supported but will in the future.

For information on localizing in your server's language, see <https://github.com/PokeNavBot/pokenav-translations>.

### Reward Aliases

The following are a list of aliases and artwork supported for all research rewards 

```eval_rst
.. csv-table:: Supported Rewards
   :header: "Reward", "Aliases", "Artwork?"
   :widths: 10, 15, 3

   Silver Pinap Berry, Silver Pinap Berries | Silver Pinap(s), ✅
   Golden Razz Berry, Golden Razz Berries | Golden Razz(s), ✅
   Razz Berry, Razz Berries | Razz(s), ✅
   Pinap Berry, Pinap Berries | Pinap(s), ✅
   Nanab Berry, Nanab Berries | Nanab(s), ✅
   Pokeball, Poke ball(s) | Pokeball(s) | Poké ball(s) | Pokéball(s),  ✅
   Greatball, Great ball(s) | Greatball(s),  ✅
   Ultraball, Ultra ball(s) | Ultraball(s),  ✅
   Stardust, Stardust, ✅
   Rare Candy, Rare Candies, ✅
   ???, Unknown | u | ?, ❌

```

For language specific localizations, see <https://github.com/PokeNavBot/pokenav-translations>.
