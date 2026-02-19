# jinja.loop
Jinja Template to build interfaces in Fortimanager<br>
Build scripts will Iterate over list of dictionaries from main.j2 containing FMG MetaVars.<br> 
<br>
Required metavars "*_metavar" below for as is operation:<br>
- main.j2 contains list of dictionaries key:value<br>
- main is imported into either vlan or iface build scripts.<br>
- build scripts loop through list building interfaces only if name:*_name is defined for device<br>
- build scripts build DHCP servers if flagged dhcp = y<br>
- build script sets vrf if vrf:*_vrf is defined<br>
<br>
example main:

```jinja
{%- set nets = 
  [
        {'name':network1_name, 'port':network1_port, 'netid':network1_netid, 'subnet':network1_subnet, 'dhcp':network1_dhcp, 'vrf':network1_vrf},
        {'name':network2_name, 'port':network2_port, 'netid':network2_netid, 'subnet':network2_subnet, 'dhcp':network2_dhcp, 'vrf':network2_vrf},
  ]
-%}
```
#### todo:
combine build script for vlan and physical insterfaces.
