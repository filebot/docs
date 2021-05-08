# FileBot Command-Line Usage Examples


## Rename TV Series episode files


#### Select and match a specific set of files with a specific series:
```sh
filebot -rename -r /input --file-filter "fn =~ /^B5/" --db TheTVDB --q 70726 -non-strict
```
```
[TEST] from [B5.1x01.mkv] to [Babylon 5 - 1x01 - Midnight on the Firing Line.mkv]
⋮
```


## Rename Anime episode files


#### Select and match a specific set of files from the current working directory with a specific series and season:
```sh
filebot -rename *Railgun*S* --db TheTVDB --q "A Certain Scientific Railgun" --filter "s == 2" -non-strict
```
```
[TEST] from [Toaru Kagaku no Railgun S - 01.mkv] to [A Certain Scientific Railgun - 2x01 - Railgun.mkv]
⋮
```

#### Use AnimeList mapper to translate AniDB naming and numbering to TheTVDB naming and numbering:
```sh
filebot -rename *.mkv --db TheTVDB --mapper AnimeList.AniDB -non-strict
```
```
[TEST] from [Nisemonogatari - 01.mkv] to [Monogatari - 2x01 - Karen Bee - Part 1.mkv]
⋮
```


## Rename Movie files


#### Rename a movie file by numeric ID:
```sh
filebot -list --db TheMovieDB --q 19995 --format "{ny} [M{id}]" -rename "a.mkv"
```
```
[TEST] from [a.mkv] to [Avatar (2009) [M19995].mkv]
```


## Rename generic files


#### Rename video files using the name of the parent folder:
```sh
filebot -rename -r /input --file-filter f.video --db file --format "{folder.name}"
```
```
[TEST] from [Avatar/a.mp4] to [Avatar/Avatar.mp4]
⋮
```

#### Move files into folders using the file name as folder name:
```sh
filebot -rename -r /input --file-filter f.video --db file --format "{fn}/{fn}"
```
```
[TEST] from [Avatar.mp4] to [Avatar/Avatar.mp4]
⋮
```


## Find files and print file information


#### Find incomplete or truncated media files:
```sh
filebot -mediainfo -r /input --filter media.IsTruncated --format {f}
```


## Find files and execute commands


#### Transcode subtitle files to SRT format / UTF-8 encoding:
```sh
filebot -mediainfo -r /input --apply srt
```


# Notes

* The `-rename` commands listed above use `--action TEST` and `--log INFO` to reduce console log verbosity.
