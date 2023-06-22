# Port-Mapping-Planner

This is a port mapping planner powered by Ansible.

It identifies the interface details of the legacy Cisco devices in thousands of retail stores in order to migrate to Juniper Networks.

This project basically is developed for the following functions
* Crawling from a seed switch in each store to get a full switch inventory
* Get interface list with vlan convertion from Cisco to Juniper
* Identyfy the neighbour devices for specific ports
* Perfrom sanity check for particular port configuration
* Distinguish primary and secondary IP address on the ports
* Provide DHCP reservation information
* Estimate AP numbers on particular trunk ports
* Provide ACL information
* Provide IP reservation for client MAC with converted IP

![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/d25d617a-b660-4881-b775-851741990670)

![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/6b31be00-5635-4b13-bfb8-92f8bd6ab85b)

![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/d1e1df3c-52fc-4dca-9cf5-faf115e2e771)

![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/9f29d698-550f-47c3-829f-4640759befea)

![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/14e379d3-5078-4140-afab-352a40a183bf)


The stores are divided in western banner and eastern banner. Each banner has different requirements.

Check out [western-banner/](western-banner/) or [eastern-banner/](eastern-banner/) for more details.

