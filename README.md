# obslab

- Prometheus
- Grafana
- Alertmanager
- Prometheus exporters:
    - node-exporter

Steps:

    $ git clone https://github.com/pathcl/obslab.git
    $ cd obslab
    $ pip3 install ansible==2.10.7 --user
    $ pip3 install jmespath==0.10.0 --user

Note: check host_ip address in line 4 & 5 Vagrantfile (replace 192.168.1.34)

    $ vagrant up

## Why?

