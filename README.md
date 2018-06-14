# fireball-ansible

This is an ansible role for using in server installation / update playbooks.

Usage:
```
    - role: fireball
      fireball_version: "0.14.1"
      fireball_release: "dev"
      fireball_os: "ubuntu14.04"
      fireball_arch: "x86_64"
      fireball_log_file: "/var/log/fireball/fireball.log"
      fireball_log_file_dir: "/var/log/fireball"
      fireball_remote_retry: "4320"
      fireball_remote_connect_timeout: "5"
      fireball_remote_retry_delay: "5"
      tags:
        - fireball
```

# support

For assistance and support please contact us at support@masterypack.com
