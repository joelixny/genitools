# scrotum
### Script to take screenshots and show a preview using dzen.
```
Usage: scrotum [options]          # Takes a screenshot
Usage: scrotum (file) [options]   # Uses a local file
                                  # General Options
-d |--directory (dir)             Directory to store the screenshot
-f |--font (name)                 Name of the font to use
-fh|--font-height (height)        Font height in pixels !IMPORTANT!
-bg|--background (hex RGB)        Background color
-fg|--foreground (hex RGB)        Text color
-S |--size (percent)              Thumbnail size in percent points of the original
-t |--time (seconds)              Time the preview will be displayed
-F |--format (xpm|xbm)            Thumbnail format
-U |--shaft                       Upload screenshot or file to Teknik using shaft and copies link to clipboard
--                                Forward the rest of the arguments to shaft
                                  # Screenshot specific options
-s |--select                      Select region to screenshot
-u |--focused                     Screenshot focused window
```

## Dependencies
##### Required
  * [scrot](https://github.com/dreamer/scrot)
  * [dzen](https://github.com/robm/dzen)
  * [ImageMagick](https://github.com/ImageMagick/ImageMagick)
##### Optional
  * [shaft](https://github.com/joelixny/genitools/tree/master/shaft) - for uploading

## Config file and options

The config file is located in `~/.genitools/scrotum.conf`. It accepts all the general options as variables, and some functions. Here are the options that can be set, listed first with the config variable name, then the short flag, and finally the long flag.


### Options
`DIRECTORY=   | -d  | --directory`
The directory in which the script will work. If taking a screenshot, it will be saved here. This setting is overwritten with the current directory if in local file mode. Example: `--directory ~/Pictures/Screenshots`.

`FONT_NAME=   | -f  | --font`
The font to use for the dzen preview. Uses the same format as dzen's -fn option. Example `--font -*-Terminus-*-*-*-*-12-*-*-*-*-*-*-*`.

`FONT_HEIGHT= | -fh | --font-height`
The height of the font in pixels for the dzen preview. This is important, if this setting isn't correct the image will not display correctly. Default value is 12. Example: `--font-height 12`.

`BACKGROUND=  | -bg | --background`
The background color to be used on the dzen preview. Uses RGB hex format. Example: `--background #000000`.

`FOREGROUND=  | -fg | --foreground`
The text color to be used on the dzen preview. Uses RGB hex format. Example: `--foreground #FFFFFF`.

`SIZE=        | -S  | --size`
The size of the dzen preview, relative to the original image. Accepts percent points, without the percent sign. Example: `--size 10`.

`TIME=        | -t  | --time`
The time the dzen preview will remain on screen, in seconds. Example: `--time 6`.

`FORMAT=      | -F  | --format`
The format of the thumbnail. This can be X PixMap (xpm) or X BitMap (xbm). Example: `--format xpm`.

`             | -s  | --select`
Allows you to select with your mouse the region of the screen to screenshot. Works like `scrot`'s option with the same names. Does not take any arguments. Example: `--select`.

`             | -u  | --focused`
Takes the screenshot of only the focused window. Works like `scrot`'s option with the same names. Does not take any arguments. Example: `--focused`.


### functions
These functions can be set on the config file to extend functionality or to modify built in functionality. The functions followed by a `*` are built into the script, and you should be careful with overwritting them.
`pre_screenshot()`
Runs before taking the screenshot. It resides inside `screenshot()*`.

`post_screenshot()`
Runs after taking the screenshot. It resides inside `screenshot()*`.

`pre_thumbnail()`
Runs before creating the thumbnail. It resides inside `preview()*`.

`post_thumbnail()`
Runs after creating the thumbnail. It resides inside `preview()*`.

`pre_dzen()`
Runs before dzen, but after all its local values have been calculated. It resides inside `preview()*`.

`post_dzen()`
Runs after dzen, but before the thumbnail file is deleted. It resides inside `preview()*`

`pre_upload()`
Runs before the file is uploaded. It resides inside `preview()*`

`post_upload()`
Runs after the file is uploaded. It resides inside `preview()*`

`help()*`
Displays the help message.

`function_exists()*`
Checks if functions are declared.

`screenshot()*`
Takes the screenshot.

`preview()*`
Creates a thumbnail, calculates the size values, and runs the dzen preview.