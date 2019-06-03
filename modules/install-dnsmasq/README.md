# Dnsmasq Install Script

This folder contains a script for installing Dnsmasq and configuring it to forward requests for a specific domain to Consul. This way, you can easily use Consul as your DNS server for domain names such as `payment.service.consul`, where `payment` is a service registered with Consul. All other domain names will continue to be resolved via the default resolver on your OS.

## Quick start

Download and run the `install-dnsmasq` script:

```
terraform-aws-consul/modules/install-dnsmasq/install-dnsmasq
```

Note: by default, the `install-dnsmasq` script assumes that a Consul agent is already running locally and connected to 
a Consul cluster. After the install completes, restart `dnsmasq` (e.g. `sudo /etc/init.d/dnsmasq restart`) and queries 
to the `.consul` domain will be resolved via Consul:

```
dig payment.service.consul
```


## Command line Arguments

The `install-dnsmasq` script accepts the following arguments:

* `consul-domain DOMAIN`: The domain name to point to Consul. Optional. Default: `consul`.
* `consul-ip IP`: The IP address to use for Consul. Optional. Default: `127.0.0.1`. This assumes a Consul agent is 
  running locally and connected to a Consul cluster.
* `consul-dns-port PORT`: The port Consul uses for DNS requests. Optional. Default: `8600`.

Example:

```
install-dnsmasq
```
