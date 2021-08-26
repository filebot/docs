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

#### Add alias names to the file name, original name and Chinese name if different from the main title:
```groovy
{ ny } 
{ allOf{ primaryTitle }{ localize.zho.n }.joiningDistinct(', ', '[', ']'){ n.contains(it) ? null : it } }
```
```
Sissi: The Young Empress (1956) [Sissi - Die junge Kaiserin, 茜茜公主2：年轻的皇后]
⋮
```
