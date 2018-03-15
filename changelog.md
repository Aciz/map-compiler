# Version 0.1.0

### Q3map2

* Fixed `surfaceparm donotenterlarge` being misspelled as `surfaceparm nonotenterlarge` 
* Fixed `odd lump size in lump 17` error whilst trying to decompile a bsp [#21](https://github.com/isRyven/map-compiler/pull/21)
* Added `-outfile <path>` flag to specify conversion operation output path [#22](https://github.com/isRyven/map-compiler/pull/22)
* Added `-automapcoords` flag to injects automatically calculated map coordinates in a compiled map as `mapcoordsmins`/`mapcoordsmaxs` keys. [#33](https://github.com/isRyven/map-compiler/pull/33)
* Added `-automapcoordspad` to set extra padding around automatically calculated map coords in a percentage form, expects normalized values. The final padding is calculated relatively to the map size. (eg. `0.05` -> 5% of the map bounding size) [#36](https://github.com/isRyven/map-compiler/pull/36)
* Fixed lightgrid calculation was working wrong (in compare to stock compiler), also making other lightgrid flags to work incorrectly(`-griddirectionality`, `-gridambientdirectionality`) [#36](https://github.com/isRyven/map-compiler/pull/36)
* Removed `-novertex` flag due to not being implemented anywhere (even in stock) [#37](https://github.com/isRyven/map-compiler/pull/37)
* Removed `-fastallocate` flag, fast allocation is now enabled by default [#39](https://github.com/isRyven/map-compiler/pull/39)
* Changed `-lightanglehl` flag to not accept value anymore, was pretty useless anyways [#39](https://github.com/isRyven/map-compiler/pull/39)
* Fixed `q3map_foliage` not generating foliage correctly [#40](https://github.com/isRyven/map-compiler/pull/40)
* Fixed infinite loop on compiler flags injection that contains forbidden characters [#42](https://github.com/isRyven/map-compiler/pull/42)

# Version 0.0.1

### Q3map2

* Increased `MAX_IMAGES` to __2048__ 
* Fix BSP compile on leaked maps
  * This allows ASE/OBJ model conversion when the model is built into void. This is how GtkRadiant's q3map2 behaves.
* ASE/OBJ model conversion straight from .map file [#11](https://github.com/isRyven/map-compiler/pull/11)
  * Syntax: `-convert -format [format] [bsp options] [path/to/file.map]`
* Adjusted `floodlight` algorithm to prevent overbrighting of styled lightmaps [#12](https://github.com/isRyven/map-compiler/pull/12)
* Added `-nofloodlight` switch to disable floodlighting [#12](https://github.com/isRyven/map-compiler/pull/12)
* Added `-nofloodstyles` switch to disable floodlighting on styled lightmaps [#12](https://github.com/isRyven/map-compiler/pull/12)
* Fixed `-nostyles` switch [#13](https://github.com/isRyven/map-compiler/pull/13)
* Added support for `$whiteimage` and `*white` values for `q3map_lightImage` [#15](https://github.com/isRyven/map-compiler/pull/15)
* Added `_bounceColor` worldspawn key to set global color value used for radiosity lighting [#16](https://github.com/isRyven/map-compiler/pull/16)
  * Shaders with `q3map_lightImage` will ignore this and use the specified image for radiosity color instead
* Disabled `-connect` functionality. XML broadcasting is disabled, and in future be either removed or replaced. This means, as of current version, you should not use compiler with Radiant, as it won't be able to print any output in logging window.
