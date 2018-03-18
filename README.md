# reaticulate-banks
banks for reaticulate extension of Reaper

## disclamer
This banks are not like built-in reaticulate banks. They not suited for factory instruments, but, generally, more complex and customized solution for making templates with optimal ergonomic (for particularly my style of work).

Solution for each library consists of:
- reaticulate bank, content of which has to be copied to your Reaticulate.reabank file. **check for banks numbers for avoiding conflicts with other banks**
- vienna ensemble project (we're working with vienna, yep?)
- rtrack-templare file, consists of tracks and vienna plugin with it's preferences
- kontakt multi for each kontakt instantion inside vienna
- personal libraries JSFX plugins, if needed for placing them after reaticulate JSFX

# instalation

- copy JSFX of desired library solution to your reaper effects folder (can be accessed with "show reaper resource path" action).
- copy contents of solution bank to the reaticulate bank with checking bank numbers
- load rtrack-template file
- if something haven't loaded, read build vienna with solution multis, being guided by solution readme
