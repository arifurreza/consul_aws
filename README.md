# Consul AWS
Automate the creation of a Consul cluster

# Consul AWS Module

This repo contains a set of modules in the [modules folder](https://github.com/arifurreza/devops_challenge_clark/tree/master/modules) for deploying a [Consul](https://www.consul.io/) cluster on [AWS](https://aws.amazon.com/) using [Terraform](https://www.terraform.io/). Consul is a distributed, highly-available tool that you can use for service discovery and key/value storage. A Consul cluster typically includes a small number
of server nodes, which are responsible for being part of the [consensus quorum](https://www.consul.io/docs/internals/consensus.html), and a larger number of client nodes, which you typically 
run alongside your apps:

![Consul architecture](https://github.com/arifurreza/devops_challenge_clark/blob/master/_docs/consul_architecture.png?raw=true)



## How to use this Module

This repo has the following folder structure:

* [modules](https://github.com/arifurreza/devops_challenge_clark/tree/master/modules): This folder contains several standalone, reusable, production-grade modules that you can use to deploy Consul.
* [examples](https://github.com/arifurreza/devops_challenge_clark/tree/master/examples): This folder shows examples of different ways to combine the modules in the `modules` folder to deploy Consul.

To deploy Consul servers for production using this repo:
   
1. Deploy Pre built AMI across an Auto Scaling Group using the Terraform [consul-cluster module](https://github.com/arifurreza/devops_challenge_clark/tree/master/modules/consul-cluster) 


## Code included in this Module:

* [consul-cluster](https://github.com/arifurreza/devops_challenge_clark/tree/master/modules/consul-cluster): The module includes Terraform code to deploy a Consul AMI across an [Auto 
  Scaling Group](https://aws.amazon.com/autoscaling/). 

* [install-dnsmasq module](https://github.com/arifurreza/devops_challenge_clark/tree/master/modules/install-dnsmasq): Install [Dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html)
  and configure it to forward requests for a specific domain to Consul. This allows you to use Consul as a DNS server
  for URLs such as `payment.service.consul`.

* [consul-iam-policies](https://github.com/arifurreza/devops_challenge_clark/tree/master/modules/consul-iam-policies): Defines the IAM policies necessary for a Consul cluster. 

* [consul-security-group-rules](https://github.com/arifurreza/devops_challenge_clark/tree/master/modules/consul-security-group-rules): Defines the security group rules used by a 
  Consul cluster to control the traffic that is allowed to go in and out of the cluster.

* [consul-client-security-group-rules](https://github.com/arifurreza/devops_challenge_clark/tree/master/modules/consul-client-security-group-rules): Defines the security group rules
  used by a Consul agent to control the traffic that is allowed to go in and out.





