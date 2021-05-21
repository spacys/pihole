# pihole - RegEx entries
## Blocking with RegEx
The idea is to block with regex instead of millions of DNS entries in blocklist to keep the clients clean and pihole smart enough.

All my blocklists has a data volume of ~320MB, in total 8.6 mio entries. Some of these are really valueable blocklists,
some others are blocking too much and in some are wrong entries between the correct ones.

After some analysis of these lists I created the regex plus some others I found in the net.  ;-)
Now I have just these regex in place, no blocklists anymore and it looks good at the moment.

In the list are:
- Top Level Domain (TLD) blocks
- Domain blocks
- Domain pattern blocks