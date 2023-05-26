# Port-Mapping-Planner

This is a port mapping planner powered by Ansible.

It is mainly used for providing interface details of the legacy Cisco devices in over 1000 retail stores in order to migrate to Juniper Networks.

This project basically is developed for 2 functions
* play1 - Crawling from a seed switch in each store to get a full switch inventory

![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/2f74ade4-d218-4915-aff9-491c00980f21)

* play2 - Get interface list with vlan convertion from Cisco to Juniper

![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/8d0f7887-94a0-454a-bb65-2c4e26e8ff3e)

Check out western-banner/ or eastern-banner/ for more details.

