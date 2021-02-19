# FileBot Custom Format Examples


## Basic Formats


#### Plex Path
```groovy
{ plex }
```
```
Movies/Avatar (2009)/Avatar (2009)
TV Shows/Alias/Season 01/Alias - S01E01 - Truth Be Told
```


#### Plex Name
```groovy
{ plex.name }
```
```
Avatar (2009)
Alias - S01E01 - Truth Be Told
```


#### Plex Path Tail
```groovy
{ plex.tail }
```
```
Avatar (2009)/Avatar (2009)
Alias/Season 01/Alias - S01E01 - Truth Be Told
```


## Advanced Snippets

#### Add 2-character language code for subtitles:
```groovy
{ '.' + lang.ISO2 }
```
```
.en
```


#### Separate Anime and non-Anime into different folders:
```groovy
{ anime ? 'Anime' : 'TV Shows' }
```
```
Anime
TV Shows
```


#### Add Dual and Multi if there are 2 or more audio languages:
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
Movies
```


#### Map AniDB episode information to TheTVDB episode information:
```groovy
{ db.TheTVDB.plex.name }
```
```
Sword Art Online - S04E23 - New World
```
