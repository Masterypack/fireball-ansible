# fireball-ansible

This is an ansible role for using in server installation / update playbooks.

Usage:
```
    - role: fireball
      fireball_log_file: "/var/log/fireball/fireball.log"
      fireball_log_file_dir: "/var/log/fireball"
      fireball_remote_retry: "4320"
      fireball_remote_connect_timeout: "5"
      fireball_remote_retry_delay: "5"
      fireball_download_url: ""
      fireball_download_user: ""
      fireball_download_password: ""
      tags:
        - fireball
```

# introduction

The main philosophy for Fireball is to rely on system facilities as much as possible instead of implementing own facilities inside the program (e.g. working with pid files, daemon modes, configuration reading, log files, etc.).

Fireball is designed primarily as CLI application in order to have a lower entry level for usage.

# Supported operating systems

All sciprts were optimized and tested to work on Ubuntu 18.04 LTS. They might work on other similar systems but were not tested to do so.

Even though originally it was designed to work on Ubuntu 14.04 LTS, that verions is slowly being phased out as that version of the OS is not supported anymore (End-of-Life).

Please create a GitHub issue if something is not working as intended for you!

# /etc/fireball files

"/etc/fireball/remote" file can contain URLs for remote playbooks. It should look like the following:
```
url="https://storage.googleapis.com/masterypack/fireball/playbooks/standard-init.fireball.gz"
url="https://storage.googleapis.com/masterypack/fireball/playbooks/standard-init.fireball.gz"
```

The following locations are for normal local playbooks:
 - "/etc/fireball/play.fireball"
 - "/etc/fireball/play.fireball.d/*.fireball"
 - "/etc/fireball/play.fireball.d/*.fireball.gz"


# other locations

 - /etc/fireball

 - /usr/bin/fireball

 - /var/run/fireball.pid

 - /var/log/fireball/

As the init script (/etc/init.d/fireball) is based on `find`, a tree configuration structure for /etc/fireball is possible (recommended actually!).

Feel free to use subdirectories for ordering:

 - /etc/fireball/play.fireball.d/00-configs/standard-1.fireball

 - /etc/fireball/play.fireball.d/01-configs/standard-1.fireball
  
# support

For assistance and support please contact us at support@masterypack.com
