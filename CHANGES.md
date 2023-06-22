FileBot 5.1.0
=============
* Support [custom post-processing scripts](https://www.filebot.net/forums/viewtopic.php?t=13769)
* Improved support for `xfs` and `bcachefs`
* Added `{tvdbid}` binding
* Added `{medium}` binding


FileBot 5.0.3
=============

* Use `Series Name (Year)` naming in the `{kodi}` binding
* Use `--action` for `--apply import` file operations
* Improved support for `.xattr` folders with `--apply import` and `--apply prune` post-processing features
* Improved support for [external format files](https://www.filebot.net/forums/viewtopic.php?t=10839)


FileBot 5.0.0
=============
* Added support for `Digital` and `Production` and `Story Arc` episode order preferences
* Added [Default Presets](https://www.filebot.net/help/presets.html) for assorted use cases
* Added `Group ➔ Double Episodes` to `Episodes` context menu
* Added `{jellyfin}` binding (i.e. [Jellyfin naming standard](https://www.filebot.net/forums/viewtopic.php?t=4116))
* Added `{acf}` audio channel format tag binding
* Added `{ct}` file creation date binding
* Added `{relativeFile}` relative library path binding
* Enhanced `{hd}` with support for additional HD resolutions (i.e. `UHD` / `QHD` / `FHD` / `HD` / `SD`)
* Enhanced `Match` auto-align behaviour
* Added `column edit` behaviour to `Edit Name`
* Added [`CTRL+O`](https://www.filebot.net/forums/viewtopic.php?t=12703) and [`CTRL+L`](https://www.filebot.net/forums/viewtopic.php?t=12703) keyboard shortcuts for `Open` and `Reveal`
* Added [`CTRL+M`](https://www.filebot.net/forums/viewtopic.php?t=12703) and [`CTRL+N`](https://www.filebot.net/forums/viewtopic.php?t=12703) keyboard shortcuts for `Edit Match` and `Edit Name`
* Support for setting `POSIX permissions` via [`--apply chmod`](https://www.filebot.net/forums/viewtopic.php?t=11079)
* Support for `Extras` via [`--apply import`](https://www.filebot.net/forums/viewtopic.php?t=11079)
* Support for [custom `--apply` actions](https://www.filebot.net/forums/viewtopic.php?t=11079)
* Support for [custom `--conflict` actions](https://www.filebot.net/forums/viewtopic.php?t=12891)
* Support for transcoding `TMPlayer` and `MPL2` subtitle files to `SRT / UTF-8`
* Enable `TheTVDBv4` by default
* Enable `HTTP/2` by default
* Fix drag-n-drop issues on Linux / KDE / Dolphin


FileBot 4.9.6
=============
* Added `Open` / `Reveal` / `Rename` / `Move to Trash` / `Set Attributes` context menu
* Added `autofill` behaviour to `Edit Match` and `Edit Name`
* Added `{sn}` season name binding
* Added `{mediaTags}` embedded media tags binding
* Added `{certification}` and `{info.certifications}` bindings for `TheMovieDB` episode information
* Added `Media` table to `Match Details` view
* Improved `Conflict` resolution messages
* Improved support for `{plex.id}` style file paths
* Experimental support for `TheTVDBv4`
* Enhanced `FileDialog` implementation on Linux
* Support for updating the `Last-Modified` time stamp via [`--apply touch`](https://www.filebot.net/forums/viewtopic.php?t=11079)
* Support `--` stop option parser convention
* Support `Open With` menu on macOS
* Support `Apple Silicon`
* Support `Java 17`


FileBot 4.9.4
=============
* Support `find-as-you-type` in `Edit Match`
* Toggle `Match Details` view via [`F6`](https://www.filebot.net/forums/viewtopic.php?t=12703) keyboard shortcut
* Improved grouping and sorting for custom [Presets](https://www.filebot.net/forums/viewtopic.php?t=3228)
* Added `{drive}` drive letter / network share / mount point binding
* Added `{vbr}` video bitrate and `{abr}` audio bitrate bindings
* Added `{vcf}` video compression format and `{ar}` aspect ratio bindings
* Added `{country}` production country binding
* Enhanced and more versatile `{plex}`, `{kodi}` and `{emby}` bindings
* Use smart unit types for `{bitrate}`, `{bytes}`, `{fps}`, `{af}` and `{channels}` bindings
* Added [`-find -exec`](https://www.filebot.net/forums/viewtopic.php?t=12622) command
* Support for adding `Finder` tags on macOS via [`--apply finder`](https://www.filebot.net/forums/viewtopic.php?t=12654)
* Support for transcoding subtitle files to `SRT / UTF-8` via [`--apply srt`](https://www.filebot.net/forums/viewtopic.php?t=11079)
* Support `--db TheMovieDB` in [`-list -rename`](https://www.filebot.net/forums/viewtopic.php?t=12553) commands
* Support `Virtual Terminal Sequences` on `Windows 10`
* Support `Remote Desktop` via [`filebot-xpra`](https://github.com/filebot/filebot-docker#readme) docker container
* Support `Java 16`


FileBot 4.9.3
=============
* Enhanced `Dark Mode` on Windows and macOS
* Enhanced `FileDialog` implementation on Windows
* Enhanced `Progress Monitor` for long-running post-process operations
* Adaptive cache update and flush
* Added `{info.video}` and `{info.status}` extended metadata bindings
* Added `{files}` binding to list directory contents and archive contents
* Enhanced `--apply prune` to delete only truly empty folders (i.e. no hidden files)
* Enhanced `--apply tag` to support cover artwork attachments
* Enhanced `--apply cover` and `--apply artwork` selection order
* Added support for `.heic` image files
* Reduced image size and memory usage
* Support `Synology DSM 7.0`


FileBot 4.9.2
=============
* Enable `Dark Mode` by default on Windows and macOS (depending on system settings)
* Enhanced `Progress Monitor` and `Dialog` UI
* Enhanced native `Desktop` integration
* Enhanced configuration options for `Presets`
* Improved support for `Export` and `Restore` of [`User Data`](https://www.filebot.net/forums/viewtopic.php?t=4205)
* Improved support for `multi-monitor` environments
* Restore `window bounds` and `window state` on startup (and actively prevent off-screen windows)
* Added `{decade}` convenience binding (e.g. `1970`)
* Added `{anime}` boolean binding (i.e. best guess based on database, genre, language, country, etc)
* Improved support for `3-digit` and `4-digit` season numbers
* Improved support for `DE-ASCII` transliteration (e.g. `ÄäÖöÜüß`)
* Enhanced `file path validation` on Linux (e.g. `GVFS`)
* Enhanced `xattr` and `crc32` in-memory cache invalidation
* Optimize `History` write operations
* Added `-d` option (i.e. `Folder Mode`)
* Added `-revert` command default behaviour (i.e. revert most recent `-rename` operation)
* Enhanced [`--q`](https://www.filebot.net/forums/viewtopic.php?t=12043) query expressions
* Enhanced [`--mapper`](https://www.filebot.net/forums/viewtopic.php?t=10996) capabilities
* Improved support for [`--mode interactive`](https://www.filebot.net/forums/viewtopic.php?t=4398) on Windows
* Improved support for [`@files`](https://www.filebot.net/forums/viewtopic.php?t=3244) (e.g. [`BOM`](https://en.wikipedia.org/wiki/Byte_order_mark))
* Improved support for `hardlink` deduplication
* Added support for `macOS Big Sur`


FileBot 4.9.1
=============
* Added `Edit Format` / `Edit Match` / `Edit Name` context menu
* Added `Smart Mode: Attributes` matcher (i.e. `xattr / exif / id3 / atom`)
* Use [`F2`](https://www.filebot.net/forums/viewtopic.php?t=2072) shortcut for `Plain File Mode`
* Use [`F3`](https://www.filebot.net/forums/viewtopic.php?t=2072) shortcut for `Local Xattr Mode`
* Enable selected post-processing features via [`Filter ➔ Attributes ➔ Apply`](https://www.filebot.net/forums/viewtopic.php?t=11079)
* Enable `clone` (on `macOS / apfs`) and `reflink` (on `Linux / btrfs`) by default for all `COPY` operations
* Enhanced `Selection Dialog` with thumbnails and tooltips
* Enhanced `Conflict Dialog` with detailed explanations
* Enhanced `manual search` to support both `search by name` and `lookup by id`
* Improved support for mapping episode information between different databases and numbering schemes (e.g. via `AnimeList` or `XEM`)
* Added `{db}` dynamic binding (e.g. map between `TheTVDB` and `AniDB` episode objects)
* Added [`{vs}`](https://www.filebot.net/forums/viewtopic.php?t=11265) standard media `{source}` tag
* Enhance `{primaryTitle}` to yield `AniDB` `x-jat` (romanized Japanese) series name for `TheTVDB` episode objects
* Enhance `{hours}` to use [Ratio (U+2236)](https://unicode-table.com/en/2236/) instead of [Colon (U+003A)](https://unicode-table.com/en/003A/)
* Added `{historic}` dynamic binding for looking up the original file path of `{f}` (e.g. `{historic.f}` is useful for `-exec` post-processing commands)
* Evaluate `{closures}` automatically in `String.plus(Closure)` constructs (e.g. `{"[" + {n} + " " + {s00e00} + "]"}`)
* Improved `-mediainfo -exec` pipeline
* Added `-no-probe` option to disable media parser (e.g. match files without reading file contents)
* Added `-no-index` option to disable local media indices (i.e. improved support for low-memory devices)
* Added `-no-history` and `-clear-history` options
* Support dynamic code evaluation via [`include`](https://www.filebot.net/forums/viewtopic.php?t=10839) and [`evaluate`](https://www.filebot.net/forums/viewtopic.php?t=10839) 
* Support `@file.groovy` syntax in `Format Editor` and `Preset Editor` (e.g. `@/path/to/MyFormat.groovy`)
* Added [`--apply`](https://www.filebot.net/forums/viewtopic.php?t=11079) option (e.g. `--apply artwork nfo url metadata`)
* Added [`--mapper`](https://www.filebot.net/forums/viewtopic.php?t=10996) option (e.g. `--mapper AnimeList.AniDB`)
* Allow `*.groovy` files as argument value for `--format`, `--filter`, `--mapper` and `--file-filter` options (e.g. `--format /path/to/MyFormat.groovy`)
* Support movie hash lookup via `--db OpenSubtitles`
* Support `-r` and `--file-filter` for `-script` calls (i.e. select files before calling the script)
* Support `bash_completion`


FileBot 4.8.5
=============
* Port to OpenJDK 11 / OpenJFX 11
* Improved syntax highlighting for format expressions
* Improved support for rare SxE patterns (i.e. S1-01)
* Added `{kodi}` binding (i.e. Kodi naming standard)
* Added `{ci}` binding (i.e. movie collection index)
* Match `{source}`, `{group}`, `{tags}` and `{s3d}` from `{media.title}`
* *Move to Trash* action in Filter tools (e.g. batch delete clutter files)
* *Paste License Key* button to simplify license activation for users who can't receive email attachments (i.e. some email providers block `*.psm` attachments)
* Built-in Automator Workflows for macOS (i.e. easily create Quick Actions and Folder actions)
* Fix UI deadlock issues on Linux
* Fix drag-n-drop issues on Linux / KDE / Dolphin
* Support for `7z` an `unrar` executables on Linux
* Support for xattr on FreeBSD / OpenBSD / NetBSD
* Support for writing xattr metadata to plain text files (i.e. improved support for rclone and gdfs)
* Support for a Dark Mode Look-and-Feel
* Fix various mediainfo / archive extract issues on QNAP NAS (especially on x86_64 devices)
* New 32-bit Windows packages (i.e. x86 msi installer)
* New multi-arch Debian packages (i.e. support armhf and aarch64 for Raspberry Pi devices or ARM-based servers)
* New multi-arch Fedora / openSUSE / CentOS packages (i.e. RPM packages)


FileBot 4.8.2
=============
* New license model and cross-platform support for all Java 8 / Java 10 platforms
* Improved episode / movie auto-detection
* Added `{hdr}` binding
* Added `--file-filter` option (e.g. `--file-filter f.video`)
* Added `--db exif` and `--db file` in addition to `--db xattr` (i.e. command-line equivalents for Preset datasources)
* [Windows] Improved HiDPI support for non-integer scale factors (e.g. 125%)
* [Linux] Support for ffprobe as replacement for libmediainfo (i.e. for armv7 / aarch64 platforms)
* [macOS] Disable 0-termination when reading / writing xattr String values


FileBot 4.7.15
==============
* Support for CoW clones (requires `APFS` or `BTRFS`)
* Improved movie auto-detection


FileBot 4.7.10
==============
* Support the new TheTVDB JSON API
* Support the new OMDb API
* Improved CD1/2 auto-detection
* Support for custom rename actions via the `--action` option
* Support for the new `-exec` option
* Support for the `FILEBOT_OPTS` environment variable for FileBot-specific Java options
* Use GnuPG signatures for all deployment artifacts


FileBot 4.7.9
=============
* Binding `{sdhd}` has been removed in favour of `{hd}` which now supports UHD/HD/SD as possible values
* Improved support for Photo mass-renaming (e.g. added `{exif}`, `{camera}` and `{location}` bindings)
* Improved streaming behaviour for `-mediainfo` commands and `--format` expressions no longer limited by file path validation (e.g. multi-line, special characters, etc)
* Support lookup by id for -list commands (e.g. `filebot -list --q 70327`)
* Support for renaming episodes files in linear order (e.g. `-list --q 70327 -rename *.mkv`)


FileBot 4.7.8
=============
* Additional language preferences
* Additional Episode Sort Order: `Absolute Airdate Order` (useful for matching by airdate or episode title instead of SxE numbers)
* Additional bindings: `{kbps}` and `{khz}`
* Unified `{localize}` and `{order}` binding usage (e.g. `localize.zho.n` or `order.airdate.sxe`)
* Use powershell instead of cmd when executing commands on Windows (e.g. `--def exec`)
* Improved behaviour for `-rename --q` command-line usage
* Improved desktop integration for Gnome and KDE
* Improved support for Debian Linux armhf ABI (e.g. Raspberry Pi)


FileBot 4.7.5
=============
* Keyboard shortcuts for calling user-defined Presets (Numpad 1..9)
* Improved episode auto-detection
* Improved movie part index auto-detection
* Improved file sort order
* Improved bindings: `{plex}`, `{t}`, `{votes}`, `{group}`, `{tags}`, `{audioLanguages}` and `{textLanguages}`
* Support ANSI color output (if `$TERM == xterm-256color`)
* Fixed Gnome GVFS drag-n-drop issues
* Reduce xattr metadata size
* Use `xz` compression for all packages (e.g. reduce download size by 40%)


FileBot 4.7.1
=============
* Improved Windows 7/8/10 integration
* Improved auto-delete behaviour (use system trash, preserve hidden user files, etc)
* `{plex}` binding now forces Windows-compatible paths (e.g. strip colons)
* New MediaInfo bindings: `{mediaTitle}` and `{bitdepth}`
* New Info Object bindings: `{id}` (series/movie ID), `{object}` and `{type}`
* New Episode bindings: `{sc}` (season count) and `{sy}` (season years)
* Support for `--action reflink` (requires Linux and a copy-on-write filesystem)
* Improved logging and debugging options


FileBot 4.7
===========
* Smart Mode for handling Movies, TV Shows, Anime and Music all at once
* Support for Renaming Folders (i.e. auto-delete left-behind empty folders)
* Resolve relative formats against the Media root folder (instead of the parent folder)
* Send To context menu for Episodes / Filter / List panels
* Improved Filter tools
* Improved List tool
* Support for TheMovieDB in Episode Mode
* Improved movie / episode auto-detection
* Fix various OpenSubtitles Search/Download and Upload issues
* Fix various TheTVDB / AniDB / TVMaze issues
* Fix various multi-episode detection issues
* Fix various ID3 Tags lookup issues
* HiDPI icons
* Fix various UI/UX issues
* Performance and caching improvements
* Improved logging and error messages
* Plex Naming Standard binding `{plex}`
* Use range multi-episode formatting by default when using `{sxe}` or `{s00e00}` (i.e. Plex naming standard)
* `{s00e00}` binding will now evaluate to TheTVDB Airdate Season / Episode for AniDB Absolute Number Episodes
* Subtitle language auto-detection when using the `{lang}` binding
* Subtitle language / category extension binding `{subt}`
* Spoken languages binding `{languages}`
* Stereoscopic 3D binding `{s3d}`
* A-Z folder binding `{az}`
* Just-in-time localization binding `{localize}`, e.g. `{localize.German.Title}`
* Filesize bindings `{bytes}`, `{megabytes}`, `{gigabytes}`
* Generic MediaInfo bindings `{video}`, `{audio}`, etc are now multi-stream bindings (and `{videos}`, `{audios}`, etc have consequently been removed)
* Cmdline operation `-revert` to revert previous `-rename` operations
* Cmdline option `--conflict` accepts index conflict resolution behaviour
* `@file` syntax for command-line argument passing
* Scripts from the online repository (e.g. `fn:sysinfo`) are now code signed and cryptographically secured against malicious tampering (not just HTTPS transport encryption)


FileBot 4.6.1
=============
* Added support user-defined Presets for repetitive tasks
* Added support for TVmaze
* Improved support for OpenSubtitles and subtitle matching
* Improved movie / episode auto-detection
* Improved ID3 Tags music mode
* Improved cache behaviour
* Improved support for Chinese & Brazilian languages
* Added helper function `String.asciiQuotes()` for normalizing various quotation marks
* Added `{model}` binding for querying the entire rename model
* Added convenience binding `{ny}` for `Name (Year)` formats
* Added bindings `{info.budget}`, `{info.revenue}` and `{info.popularity}` to the movie info object
* Changed `String.sortName()` default behaviour
* Support `--filter` as Groovy-based file filter in `filebot -mediainfo` calls
* Use `Apache Commons VFS2` and `junrar` to reduce native dependencies on some platforms
* Support `$JAVA_OPTS` convention in all `filebot.sh` scripts
* Update to FanartTV API v3
* Codesign Windows NSIS and MSI installers
* Publish sha256 checksums for all release files
* Updated Chocolatey install scripts with sha1 checksums


FileBot 4.5.6
=============
* Improved series / episode detection
* Optimize web service calls and provide more data via xattr metadata
* Extended metadata is now fetched from the originally selected data source (e.g. AniDB "generes" is no mapped to Anime categories, etc)
* Fixed various issues related to fetching Chinese subtitles
* Allow processing of `*.ac3` and `*.dts` files in Music mode
* Do not treat folders with `movie.nfo` as single units like disk folders anymore
* Fixed lots of issues that have been raised in the forums


FileBot 4.5.3
=============
* Batch `-extract` will now only extract new files
* `Set Output Folder` button in Format Editor
* Optimizations for subtitle search and lookup
* Prevent OpenSubtitles abuse
* Require OpenSubtitles login
* New script: `fn:verify`
* Force Nimbus as default cross platform LaF (mainly applies to KDE users)


FileBot 4.5
===========
* Make sure movie name `{n}` works as per user-defined Preferred Language (only affects non-English mode)
* Support choosing between (default) `Opportunistic` / (new) `Strict` mode matching
* Improved behavior when processing large sets of files
* Improved movie / episode detection
* Improved TheMovieDB / AcoustID support
* Inherit ACLs when moving / copying files to remote folders
* New bindings `{model}` and `{self}` for advanced use-cases
* In movie mode `{primaryTitle}` now maps to original movie name
* `--db xattr` for offline processed using previously stored xattr metadata
* `--action duplicate` to duplicate files via hardlink when possible or copy when necessary
* Fixed various UI layout and LaF issues
* Improved integration with OSX
* Support passing file arguments in single-panel mode

FileBot 4.3
===========
* Lots of optimizations and usability improvements
* Dropped support for Java 7 (so Java 8 is required now)
