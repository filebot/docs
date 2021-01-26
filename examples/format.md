# FileBot Custom Format Examples


## Basic Formats


### Plex Path
```groovy
{plex}
```
```
Movies/Avatar (2009)/Avatar (2009)
TV Shows/Alias/Season 01/Alias - S01E01 - Truth Be Told
```


### Plex Name
```groovy
{plex.name}
```
```
Avatar (2009)
Alias - S01E01 - Truth Be Told
```


### Plex Path Tail
```groovy
{plex.tail}
```
```
Avatar (2009)/Avatar (2009)
Alias/Season 01/Alias - S01E01 - Truth Be Told
```


## Advanced Snippets
```groovy
{ anime ? 'Anime' : 'TV Shows' }
```
```
Anime
TV Shows
```


```groovy
{ any{ 'Movie Collection' / collection }{ 'Movies' } }
```
```
Movie Collection/Avatar Collection
Movies
```
