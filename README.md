# Archived 

Moved to [steamdeck-helpers](https://github.com/Dankoy/steamdeck-helpers)

# steamdeck-backup-services
Contains backup services for retroarch in steamdeck or other linux os


## Description

For retroarch folders beckup is used rsync

The following command copy files which exist in include statements:

`rsync -avzhm --include='saves/*' --include='screenshots/*' --include='states/*' --include='system/*' --include='retroarch.cfg' --include='*/'  --exclude='*'  /home/deck/.var/app/org.libretro.RetroArch/config/retroarch/ /home/deck/Documents/retroarch_backup/`

Also, it is necessary to create timer for backup service
`~/.config/systemd/user/some-service-name.*`


### Useful commands
1) Start service - `systemctl --user start some-service-name`
2) Enable service - `systemctl --user enable --now some-service-name.timer`
3) After each modification in service or timer - `systemctl --user daemon-reload`
