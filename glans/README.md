# glans
### Script to browse the shaft upload log.
```
Usage: glans [options] [log]      # Takes a screenshot
-f |--font (name)                 Name of the font to use
-fh|--font-height (height)        Font height in pixels !IMPORTANT!
-bg|--background (hex RGB)        Background color
-fg|--foreground (hex RGB)        Text color
-F |--format (xpm|xbm)            Thumbnail format
-p |--page (page number)          Which page to view
-g |--geometry (WidthxHeight)     The width and height for the thumbnail
```

## Dependencies
##### Required
  * [dzen](https://github.com/robm/dzen)
  * [ImageMagick](https://github.com/ImageMagick/ImageMagick)
##### Optional
  * [curl](https://github.com/curl/curl) - for files not stored locally