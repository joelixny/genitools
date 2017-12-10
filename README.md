# genitools
### Set of scripts to screenshot, upload, paste, and shorten URLs using Teknik services.

These scripts will use the shared directory `~/.genitools` for config files and auxiliary files. Please make sure to create that folder, and add the auxiliary files if you intend to use those features.

These scripts depend on each other for certain features, please add them to your `$PATH` for those features to work properly.

## scrotum
#### Script to take screenshots and show a preview using dzen.

This script looks for its config file in `~/.genitools/scrotum.conf`.

## shaft
#### Script to Upload, Paste, and Shorten URLs using Teknik services.

This script looks for its config file in `~/.genitools/shaft.conf`.
If you intend to upload files from Standard input and wish for the files to have the correct extension, download `shaft-mime-list.txt` into `~/.genitools/shaft-mime-list.txt`.
If you this script to log all uploads, run `touch ~/.genitools/shaft.log` to create the log file.

## glans
#### Script to browse the shaft upload log using a dzen window.

This script looks for its config file in `~/.genitools/glans.conf`
By default it will look for the log in `~/.genitools/shaft.log`, unless a log file is specified as an argument.
