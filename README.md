# pvcmd
pvcmd goal is to provide to PowerVC user a set of tools to work with PowerVC in command line. The code provided here are just a couple of exemple that fit my needs. Feel free to modify and change the code.
pvcmd use python httplib to work with RESTful API.

## pvcgrowlun
The goal of pvcgrowlun is to extend an already existing lun created by PowerVC this lun can be a boot or a data lun.
```
# pvcgrowlun -v multi-vol-bf697dfa-0000003a-828641A_21AFF8V-data-1 -s 84 -p powervc.lab.chmod666.org -u root -P mypassword
```
* -v: volume name
* -s: desired size
* -p: powervc url
* -u: powervc user
* -P: powervc password

## pvcmkvm
The goal of pvcmkvm is to create a virtual machine on PowerVC
```
# cat myvm
name:myvm
ip_address:10.10.10.2
vlan:vlan666
image:aix7100-03-05-chef
storage_connectivity_group:npiv_4ports
virtual_processor:1
entitled_capacity:0.1
memory:8192
storage_template:svc
# pvcmkvm -f myvm -p powervc.lab.chmod666.org -u root -P mypassword
```
* -f: file describing the Virtual machine
  + name: the hostname of the virtual machine
  + ip_address: the ip address of the virtual machine
  + image: the image used for deployement
  + storage_connectivity_group: PowerVC storage connectivity group
  + virtual_processor: number of desired virtual processor (min and max are calculated in the script)
  + entitled_capacity: number of desired entitle processing unit (min and max are calculated in the script)
  + memory: amount of memory in mb (min and max are calculated in the script)
  + storage_template: PowerVC storage template
* -p: powervc url
* -u: powervc user
* -P: powervc password
