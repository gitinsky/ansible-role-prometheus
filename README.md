# ansible prometheus role

**Role is in active development, some naming conveniences could be changed.**

This is a set of roles that currently include [prometheus](https://github.com/prometheus/prometheus),[alertmanager](https://github.com/prometheus/alertmanager), [node_exporter](https://github.com/prometheus/node_exporter) and [pushgateway](https://github.com/prometheus/pushgateway).

All of the executables have lots of command line and config options, if you miss any just add it and ensure to updated role defaults with the dafault values, PRs are welcomed.

## prometheus/prometheus

Define `prometheus_conf_template_name` to use your own template or disable it with ```prometheus_no_conf: yes``` and deploy it with your own tasks/roles.
Put your ```file_sd_configs``` to ```/etc/prometheus/file_sd_configs/*.yml``` and notify prometheus with ```runit hup prometheus```.
Put your ```rule_files``` to ```/etc/prometheus/rules/*.conf```, verify them by notifying ```prometheus check rules``` and notify prometheus with ```runit hup prometheus```.

## prometheus/alertmanager

This role installes example config for alertmanager if none is presented yet. Put your own file to ```/etc/alertmanager/alertmanager.yml``` and notify ```runit hup alertmanager```.

## prometheus/node_exporter

## requirements

- [runit](https://github.com/gitinsky/ansible-role-runit)
- [grafana](https://github.com/gitinsky/ansible-role-grafana), optional
- [vagrant](https://github.com/gitinsky/ansible-role-vagrant), optional, used for vagrant deployments.
