This is a script targeting the stores of Eastern Banner - CTR, Party City, PartSource, Petroleum

* Retrieve the interfaces status, description and their mac address on the network devices.
* Perfrom sanity check on the Dealer Lan trunk ports by scanning the interface configuration.
   * ![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/4768dbbd-0ec3-46e7-8449-5910a508afb5)
* Distinguish the primary and secondary IP address on the Dealer network interface.
   * ![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/b03939f9-cd08-4d1d-901c-cd53d86c94f2)
* Retrieve DHCP reservation information on the routers.
   * ![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/5ae1f87c-3001-4d36-9c41-2c5bd5fdc2bd)
* Identify the AP number on the swicth by checking the mac address on the trunk ports.
* Retreive the ACL configuration.
* Contruct the IP reservation based on the arp table and the converted VLAN IP:
   * ![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/59b6e543-a97f-4312-b191-4a8172969fdc)
* Identifies interfaces vlan by the following rules:
   * ![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/66365d98-353a-43d5-83c1-2c06253c928c)

Notes to create an ansible controller node on windows PC:
1. Download Vitual Box
2. Create an Ubuntu VM on top with one NAT network adaptor
3. `sudo passwd root`
4. Allow ssh and `reboot`
5. Set up port forwarding rule for ssh locally
6. `sudo apt update`
7. `sudo apt install python3-pip`
8. `python3 -m pip install ansible`
9. `ansible --version`

To run the script:
1. `cd eastern-banner`
2. `cp group_vars/all-copy.yaml group_vars/all.yaml`
3. Configure the username and password in group_vars/all.yaml
5. Make sure the targeted switch is in `inventory/hosts`. Others can be commented out or removed.
6. `sreen`
7. `rm log`
8. `ansible-playbook play0.yaml > log`
9. `Ctrl + A + D`
10. `tail -f log` to monitor the process
11. outputs are generated in `output/`


