# FileBot Command-Line Usage Examples


#### Select and match a specific set of files with a specific series:
```sh
filebot -rename -r /input --file-filter "fn =~ /^B5/" --q 70726 --db TheTVDB -non-strict --action TEST --log INFO
```
```
[TEST] from [B5.1x01.mkv] to [Babylon 5 - 1x01 - Midnight on the Firing Line.mkv]
```


#### Find incomplete or truncated media files:
```sh
filebot -mediainfo -r /input --filter media.IsTruncated --format {f}
```



#### Transcode subtitle files to SRT format / UTF-8 encoding:
```sh
filebot -mediainfo -r /input --apply srt
```
