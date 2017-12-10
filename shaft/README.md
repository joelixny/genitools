# shaft
### Script to Upload, Paste, and Shorten URLs using Teknik services.
```
Usage: shaft [options] FILE|URL # Defaults to shortening URLs or uploading FILEs
Usage: shaft [options] < data   # Defaults to pasting the data
Usage: cmd | shaft [options]    # Defaults to pasting cmd's output
                                # Genral options
-c |--clipboard                 Copy URL to clipboard instead of printing, requires xsel
-cp|--clipboard-print           Copies to clipboard and prints, --clipboard overrides this
-p |--paste                     Override mode to pasting
-u |--upload                    Override mode to uploading
-s |--shorten                   Override mode to shortening
-R |--response                  Show the json response from the server
-nt|--do-not-track              Tells Teknik to not track, in accordance to the privacy policy
-l |--login (user) (password)   Authenticate to your Teknik account
                                # Paste options
-r |--raw                       Gives link to raw paste, default if no paste options are set
-nr|--no-raw                    Gives link to normal paste, default if any paste option is set
-t |--title (title)             Title for the paste file
-S |--syntax (syntax)           Selects the syntax for the paste
-P |--password (password)       Password to lock the paste
-H |--hide                      Hides paste from public list
-eu|--expire-unit (unit)        Unit for expiration time, can be: view, minute, hour, day, month, or year
-el|--expire-length (length)    Length for expiration, both length and unit are required
                                # Upload options
-se|--server-encrypt            Encrypt files on Teknik, default option
-ne|--no-server-encrypt         Don't encrypt files on Teknik
-sd|--server-decrypt            Decrypt files on Teknik, default option, no key will be asked to view the file
-nd|--no-server-decrypt         Don't decrypt files on Teknik, a key will be asked to view the file if encrypted
-ce|--client-encrypt            Encrypt the file before uploading, requires OpenSSL
-ks|--key-size (128|192|256)    Sets the key size in bits
-ft|--file-type                 Sets the file mime type, will attempt to detect automatically if not supplied
```

## Dependencies
##### Required
  * [curl](https://github.com/curl/curl)
  * [jq](https://github.com/stedolan/jq)
##### Optional
  * [openssl](https://github.com/openssl/openssl) - for clientside encryption
  * [xxd](https://linux.die.net/man/1/xxd) - for clientside encryption
  * [xsel](https://linux.die.net/man/1/xsel) - for clipboard
