# pihole - RegEx entries
## Blocking with RegEx
The idea is to block with regex instead of millions of DNS entries in blocklists to keep the clients clean and pihole smart.

All my blocklists has a data volume of ~320MB, in total 8.6 mio entries. Some of these are really valueable blocklists,
some others are blocking too much and in some are wrong entries between the correct ones.

After some analysis of these lists I created the regex plus some others I found in the net.  ;-)
Now I have these regex in place and only few blocklists. The RegEx will be updated over the time.

In the list are:
- Top Level Domain (TLD) blocks
- Domain blocks, mainly ads and trackers
- Domain pattern blocks incl. all sub domains

Please remember, it might be possible you have to add some entries to your whitelist.
