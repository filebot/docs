# FileBot Custom Format Examples


## Movie / Episode formats


#### Plex file path
```groovy
{ plex }
```
```
Movies/Avatar (2009)/Avatar (2009)
⋮
TV Shows/Alias/Season 01/Alias - S01E01 - Truth Be Told
⋮
```

#### Plex file name
```groovy
{ plex.name }
```
```
Avatar (2009)
⋮
Alias - S01E01 - Truth Be Told
⋮
```

#### Plex file path without Movies / TV Shows folder
```groovy
{ plex.tail }
```
```
Avatar (2009)/Avatar (2009)
⋮
Alias/Season 01/Alias - S01E01 - Truth Be Told
⋮
```


## Generic file format snippets


#### Parent folder path
```groovy
{ folder }
```

#### Parent folder name
```groovy
{ folder.name }
```


## Advanced format snippets


#### Add 2-character language code for subtitle files:
```groovy
{ '.' + lang.ISO2 }
```
```
.en
⋮
```

#### Separate 4K Movies and non-4K Movies:
```groovy
{ hd == /UHD/ ? '4K Movies' : 'Movies' }
```
```
4K Movies
Movies
```

#### Add 10bit marker to high video bit depth files:
```groovy
{ bitdepth == 10 ? ' [10bit]' : null }
```
```
 [10bit]
```

#### Custom Character Replacement
```groovy
{
	n.replace(
		':' : '',
		'-' : '',
		'&' : 'and'
	)
}
```

#### Custom file size formatting with German locale preferences:
```groovy
{ bytes.MB.format('#,000.0', 'de-DE') }
```
```
307,1
⋮
```

#### Custom audio channel count formatting:
```groovy
{
	af.format(
		8: 'DD+ 7.1',
		7: '6.1', 
		6: 'DD 5.1',
		5: '5.0',
		3: '2.1',
		2: '2.0'
	)
}
```
```
DD 5.1
2.0
⋮
```

#### Add Dual and Multi for 2 or more audio languages:
```groovy
{
	def n = audioLanguages.size()
	n > 2 ? "Multi" : n > 1 ? "Dual" : null
}
```
```
Multi
Dual
```

#### Add airdate formatted with date ordinal suffix (1st, 2nd, etc) and month name:
```groovy
{
	airdate.format('d MMMM yyyy').replaceFirst(/\d+/) { d ->
		d =~ /11$|12$|13$/ ? d + 'th' : 
		d =~ /1$/ ? d + 'st' : 
		d =~ /2$/ ? d + 'nd' :
		d =~ /3$/ ? d + 'rd' :
		d + 'th'
	}
}
```
```
3rd May 2021
4th May 2021
⋮
```

#### Separate movie collections and standalone movies into different folders:
```groovy
{ any{ 'Movie Collection' / collection }{ 'Movies' } }
```
```
Movie Collection/Avatar Collection
⋮
Movies
```

#### Map AniDB episode information to TheTVDB file naming:
```groovy
{ db.TheTVDB.plex.name }
```
```
Sword Art Online - S04E23 - New World
⋮
```

#### Add alias names to the file name, original name and Chinese name if different:
```groovy
{ ny } 
{ allOf{ primaryTitle }{ localize.zho.n }.joiningDistinct(', ', '[', ']'){ n.contains(it) ? null : it } }
```
```
Sissi: The Young Empress (1956) [Sissi - Die junge Kaiserin, 茜茜公主2：年轻的皇后]
⋮
```

#### Guess source media based on resolution, bitrate and file size:
```groovy
{
	if (hd == 'SD')
		if (megabytes >= 700 && mbps >= 1.1)
			return 'DVDRip'
		else
			return 'TVRip'

	if (hd == 'HD')
		if (gigabytes >= 1 && mbps >= 18)
			return 'BDRemux'
		else if (mbps >= 8)
			return 'BDRip'
		else if (mbps >= 2.2)
			return 'MicroHD'
		else
			return 'HDRip'

	if (hd == 'UHD')
		if (gigabytes >= 1 && mbps >= 32)
			return 'UHDRemux'
		else if (mbps >= 16)
			return 'UHDRip'
		else
			return 'MicroUHD'
}
```
```
DVDRip
TVRip
BDRemux
BDRip
MicroHD
HDRip
UHDRemux
UHDRip
MicroUHD
```
