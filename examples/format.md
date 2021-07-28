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


#### Separate Anime and non-Anime episode files into different folders:
```groovy
{ anime ? 'Anime' : 'TV Shows' }
```
```
Anime
TV Shows
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
