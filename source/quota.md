# Quota

Individual quotas are a necessary evil of running a resource intensive process like screenshot analysis. Here's a full explanation of how they work in PokeNav, which attempts to balance accessibility with covering operation costs.

## How Quotas Work

All users on each server with PokeNav are given a monthly quota of **20 screenshot scans**. This quota can be easily upgraded via contributing to [Patreon](https://www.patreon.com/PokeNavBot). When an individual upgrades his quota, he may share his new monthly quota with the rest of his primary server. 

### `$quota` command

This command will show a user the amount of individual quota she has used in a month and how many remaining scans are available. Quota is reset on the first day of each month. 

### What if I run out of quota?

If a user exceeds their individual and shared quota, PokeNav will send them a DM with instructions on increasing their monthly quota via support on [Patreon](https://www.patreon.com/PokeNavBot). They will be unable to perform any action that requires scanning a screenshot.

### What does sharing quota mean?

Patreons can share their quota with their primary server using the `$share-quota` command in any channel where PokeNav is active. 

For example, if koshermuffin is a Patreon subscriber receiving 200 individual screenshot scans per month, she may use the `$share-quota` command to share the entire 200 quota with the rest of her server. Multiple people can share their quota with the server, creating a larger pool of available scans. 

If another user, IVpips, exceeds his individual quota of 20 scans in a given month, he may use up to **30 additional scans** (this number can be set by server admins) from the shared quota. 

#### `$set-member-shared-quota` command

This command allows server admins to set a restriction on the number of scans an individual may use from the shared quota. 

The default limit for this is 30 scans. If a user exceeds both their individual and shared quota, they will be directed to supporting via [Patreon](https://www.patreon.com/PokeNavBot) to increase their individual quota (and therefore be given the opportunity to also share this increased quota with their server).

This limit is there to protect your server's shared pool from being consumed by a malicious or unknowing user. 
