# FileBot Command Examples


#### Select and match a specific set of files with a specific series:
```
filebot -rename -r /input --file-filter "fn =~ /^B5/" --q 70726 --db TheTVDB -non-strict --action TEST --log INFO
```
```
[TEST] from [B5.1x01.mkv] to [Babylon 5 - 1x01 - Midnight on the Firing Line.mkv]
```
