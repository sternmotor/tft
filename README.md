tft
====

Script for transfering single or multiple files or small directories 
from one terminal session to another by standard copy-paste.

Selected files are beeing compressed (tar gzip) and converted
to ascii text (base64). This text is printed to terminal and can be copied
via terminal copy-paste and inserted into another tft instance
on a different terminal. 

Permissions and file modes are preserved . Copying works for files and small 
directories. For example scripts with a lot of line breaks are converted to 
some small lines of base64 code, easier to copy-paste. 

Call this script with specified file pathes for parallel compression or call 
this script without parameters for extracting files.

    
Usage
-----

For compression, for each FILE argument only the last path part is used. For
example `d1/d2/d3/d4` (and it's contents if this is a directory)
is archived and later extracted as `d4` in current dir.

For extended copy/paste options via Putty terminal emulator, see 
"clear scrollback buffer" and "select all" file menu options


Installation
------------

You can clone this repository or directly pull this script into `/usr/local/bin`:

    curl -L  https://raw.githubusercontent.com/sternmotor/dude/master/tft > /usr/local/bin/tft 
    chmod 0755 /usr/local/bin/tft

If `curl` is not available, use `wget`:

    wget https://raw.githubusercontent.com/sternmotor/dude/master/tft -O /usr/local/bin/tft
    chmod 0755 /usr/local/bin/tft

You may want to transfer this tool manually to another machine like

  tft "$(which tft)"

, copy base64 text to clipboard and on the other site paste copied content 
to bin dir like 

  cd /usr/local/bin
  base64 -d | tar -xz

