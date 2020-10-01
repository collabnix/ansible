# Running your first ad-hoc command

## What is ad-hoc command?

- Ad-hoc command is give you control to perform task on specific host or on all hosts, using command line
- Ad-hoc consists of host/host-group and name of module

## How to run Ad-hoc command?

Let say, u want to perform ping on localhost

```
$ ansible localhost -m ping
localhost | SUCCESS => {
    "changed": false,
    "ping": "pong"
}   
  
```
Here, we are using ping module against localhost, if you want perform same operation on N-number of hosts then simply create host-group in inventory file and replace localhost with host-group name.

## So, What is Inventory file?

- Inventory file consists of all your host info, variable, group (i.e. lets say, you have group of webserver hosts or DB server hosts) then create groups

- Inventory file located at "/etc/ansible/hosts", we can create own inventory file for different-different project.
  example: [web-server]
           ip-1
           ip-2
```
$ ansible web-server -m ping

```
The above command will apply to web-server group, likewise you can create N-number of group and perform operation on it.


## What is Modules ?

- Module is nothing but task plugins or pre-defined package contain of logic.

- To check, available modules in ansible

```
$ ansible-doc --list
  a10_server                                                    Manage A10 Networks AX/SoftAX/Thund...
  a10_service_group                                             Manage A10 Networks AX/SoftAX/Thund...
  aci_aep_to_domain                                             Bind AEPs to Physical or Virtual Do...
  aci_ap
```
This will list out all available modules (i.e Network modules, cloud modules, storage modules, linux modules..etc)

