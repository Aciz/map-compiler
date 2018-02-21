# Version 0.0.1

### Q3map2

* Increased `MAX_IMAGES` to __2048__
* Fix BSP compile on leaked maps
  * This allows ASE/OBJ model conversion when the model is built into void. This is how GtkRadiant's q3map2 behaves.
* ASE/OBJ model conversion straight from .map file
  * Syntax: `-convert -format [format] [bsp options] [path/to/file.map]`
* Adjusted `floodlight` algorithm to prevent overbrighting of styled lightmaps
* Added `-nofloodlight` switch to disable floodlighting
* Added `-nofloodstyles` switch to disable floodlighting on styled lightmaps
* Fixed `-nostyles` switch
* Added support for `$whiteimage` and `*white` values for `q3map_lightImage`
* Added `_bounceColor` worldspawn key to set global color value used for radiosity lighting
  * Shaders with `q3map_lightImage` will ignore this and use the specified image for radiosity color instead
* Disabled `-connect` functionality. XML broadcasting is disabled, and in future be either removed or replaced. This means, as of current version, you should not use compiler with Radiant, as it won't be able to print any output in logging window.
