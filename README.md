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
