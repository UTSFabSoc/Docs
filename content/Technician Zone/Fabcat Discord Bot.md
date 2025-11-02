meow meow! welcome to fabcat! a discord bot for Fabsoc made by Tabby
`Version 0.1`
## Basic Commands
This commands can be used by anyone!
- `/help`
  displays this help screen
- `/printer-status`
  displays the currently loaded spools and nozzle for each printer
- `/spool-list`
  displays a list of both loaded and available spools

## Technician Only Commands
Since these commands edit data, only users with the `technician` role may use them
### Printer Management
- `/printer-create <name>`
  Creates a new printer with the provided name
- `/printer-delete <name>`
  Deletes the printer with the matching name
- `/printer-slots <name> <slots>`
  Changes the amount of spool slots a printer has (for example: if an AMS is attached)
- `/printer-nozzle <name> <new_nozzle>`
  Changes the nozzle attached to the printer
- `/printer-load <printer-name> <spool-name>`
  Loads a spool into a printer, If the printer only has one spool slot and it is filled then this command will replace it and return the old spool to the library (offers option to delete old spool)
- `/printer-unload <printer-name>`
  Unloads the spool from the printer, If there are multiple a dropdown asks which to unload. The unloaded spool can then be kept in the library or deleted
### Spool Management
- `/spool-create <name> [link]`
  Creates a new spool with the given name and optionally a link to it
- `/spool-delete <name>`
  Deletes the spool with the matching name, can only delete a spool if it is in the library (not loaded into a printer)
- `/spool-edit <old-name> <new-name> [new-link]`
  Changes the name and/or link of a spool, only works if the spool is in the library (not loaded into a printer)
## Contributing to fabcat
- type here