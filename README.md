# pihole - RegEx entries
## Blocking with RegEx
The idea is to block with RegEx as a powerful instrument instead of millions of DNS entries in blocklists to keep the clients clean and pihole smart.

All my blocklists had a data volume of ~320MB, in total 8.6 mio entries. Some of these are really valueable blocklists,
some others are blocking too much and in some are wrong entries between the correct ones.

After some analysis of these lists, I created the RegEx entries plus some others I found in the net.
Now, with those RegEx in place, I do not use any blocklists anymore.

The files contains:
- Top Level Domain (TLD) blocks
- Domain blocks, mainly ads and trackers
- Domain pattern blocks incl. all sub domains
- Some domains which needs to be whitelisted

It might be necessary to adjust some entries based on your needs. Please note that the combination of RegEx entries offers the greatest added value.

To analyze the (allowed) called domains, pihole data can be extracted with:
```shell
sqlite3 "/etc/pihole/pihole-FTL.db" \
  "SELECT domain FROM queries WHERE STATUS IN (2, 3, 12, 13, 14) AND TYPE != 6 GROUP BY domain" > list.txt
```

After the analysis and updated RegEx entries the pihole history should be reset:
```shell
sudo service pihole-FTL stop
sudo mv /etc/pihole/pihole-FTL.db /home/<userID>/pihole-FTL_$(date +"%m-%y").db
sudo service pihole-FTL start
```
