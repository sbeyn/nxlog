# Ansible Role: nxlog

## Platform

   - Windows

## How it works

The NXLog Community Edition is one of our open source log management solutions available at no cost.
This role add just a configuration for read files log and forward the data to syslog centralized logging.
The module win_package (by Chocolatey) manage all aspects of Nxlog (installation, configuration, upgrade, and uninstallation).


## Role Main Variables

1. `nxlog_omtcp_host` (default: `localhost`): the host of syslog centralized logging.


## Role Other Variables

nxlog_root: "C:\\Program Files (x86)\\nxlog"
nxlog_moduledir: "%ROOT%\\modules"
nxlog_cachedir: "%ROOT%\\data"
nxlog_pidfile: "%ROOT%\\data\\nxlog.pid"
nxlog_spooldir: "%ROOT%\\data"
nxlog_logfile: "%ROOT%\\data\\nxlog.log"
nxlog_omtcp_host: "localhost"
nxlog_omtcp_port: 514


## Dependencies

None.

## Example Playbook

    - hosts: your-servers
      vars:
        my-tag:
          bpe_nifi_bootstrap:
            file: "C:\\\\Program Files\\\\my-application\\\\logs\\\\my-application.log"
            parameters:
              ReadFromLast: True
              SavePos: True
              Exec: '$nxtags = "my-tag";'
  
      roles:
        - { role: nxlog, nxlog_omtcp_host: "your-server-logging"}


## License

MIT

### Author Information

This role was created by [Sylvain Beynard](https://github.com/sbeyn).

