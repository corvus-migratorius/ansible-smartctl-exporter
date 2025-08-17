genlab.smartctl-exporter
=========

```smartctl``` is a command-line utility used to control and monitor the Self-Monitoring, Analysis and Reporting Technology (SMART) system in hard disk drives (HDDs) and solid-state drives (SSDs). ```smartctl-exporter``` exports ```smartctl``` statistics to Prometheus.

Requirements
------------

smartctl 

Role Variables
--------------
The exporter will scan the system for available devices if no ```--smartctl.device``` flags are used.
```yaml
---
smartctl_exp_port: 9633
smartctl_exp_args: ""
smartctl_exp_version: "0.14.0"
smartctl_exp_dir: "/etc/exporters"
smartctl_exp_config_dir: "/etc/exporters/config"
smartctl_exp_interval: "60s"
smartctl_exp_rescan: "10m"
smartctl_exp_devices: []
smartctl_exp_device_exclude: ""
smartctl_exp_device_include: ""
smartctl_exp_web_telemetry_path: "/metrics"
smartctl_exp_log_level: "info"
smartctl_exp_log_format: "logfmt"
smartctl_exp_args: # --version --web.systemd-socket 
smartctl_exp_web_config: #Path to configuration file that can enable TLS or authentication
```
Dependencies
------------

None

Example Playbook
----------------

```yaml
roles:
- role: genlab.smartctl_exporter
    smartctl_exp_version: "0.14.0"
    smartctl_exp_dir: "/etc/exporters"
    smartctl_exp_config_dir: "/etc/exporters/config"
```

License
-------

BSD

Author Information
------------------

corvus-migratorius@proton.me
