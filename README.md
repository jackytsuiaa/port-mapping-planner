# Port-Mapping-Planner

This is a port mapping planner powered by Ansible.

It identifies the interface details of the legacy Cisco devices in thousands of retail stores in order to migrate to Juniper Networks.

This project basically is developed for the following functions
* Crawl from a seed switch in each store to get a full switch inventory
* Get interface list with vlan convertion from Cisco to Juniper
* Identify the neighbour devices for specific ports
* Perfrom sanity check for particular port configuration
* Distinguish primary and secondary IP address on the ports
* Provide DHCP reservation information
* Estimate AP numbers on particular trunk ports
* Provide ACL information
* Provide IP reservation for client MAC with converted IP

The stores are divided in western banner and eastern banner. Each banner has different requirements.

Check out [western-banner/](western-banner/) or [eastern-banner/](eastern-banner/) for more details.

