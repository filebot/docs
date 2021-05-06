# FileBot Command-Line Usage Examples



#### Select and match a specific set of files with a specific series:
```sh
filebot -rename -r /input --file-filter "fn =~ /^B5/" --q 70726 --db TheTVDB -non-strict --action TEST --log INFO
```
```
[TEST] from [B5.1x01.mkv] to [Babylon 5 - 1x01 - Midnight on the Firing Line.mkv]
⋮
```



#### Select and match a specific set of files from the current working directory with a specific series and season:
```sh
filebot -rename *Railgun*S* --q "A Certain Scientific Railgun" --filter "s == 2" -non-strict --action TEST --log INFO
```
```
[TEST] from [Toaru Kagaku no Railgun S - 01.mkv] to [A Certain Scientific Railgun - 2x01 - Railgun.mkv]
⋮
```



#### Rename video files using the name of the parent folder:
```sh
filebot -rename -r /input --file-filter f.video --db file --format "{folder.name}" --action TEST --log INFO
```
```
[TEST] from [Avatar/a.mp4] to [Avatar/Avatar.mp4]
⋮
```



#### Move files into folders using the file name as folder name:
```sh
filebot -rename -r /input --file-filter f.video --db file --format "{fn}/{fn}" --action TEST --log INFO
```
```
[TEST] from [Avatar.mp4] to [Avatar/Avatar.mp4]
⋮
```


#### Find incomplete or truncated media files:
```sh
filebot -mediainfo -r /input --filter media.IsTruncated --format {f}
```



#### Transcode subtitle files to SRT format / UTF-8 encoding:
```sh
filebot -mediainfo -r /input --apply srt
```
