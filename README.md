# jinja.loop
Jinja Template to build interfaces in Fortimanager
Iterate over list of dictionaries containing FMG MetaVars. 
required metavars "*_metavar" below for as is operation:
- main.j2 contains list of dictionaries key:value
- main is imported into either vlan or iface build scripts.
- build scripts loop through list building interfaces and DHCP servers if flagged dhcp = y
```
{'name':network1_name, 'port':network1_port, 'netid':network1_netid, 'subnet':network1_subnet, 'dhcp':network1_dhcp, 'vrf':network1_vrf},
```
