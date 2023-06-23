This is a script targeting the stores of Eastern Banner.

1. Retrieve the interfaces status, description and their mac address on the network devices.
2. Perfrom sanity check on the Dealer Lan trunk ports by scanning the interface configuration.
   ![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/164fea97-3cc2-4946-bc63-e552e69d977b)
3. Distinguish the primary and secondary IP address on the Dealer network interface.
   ![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/7dd17fb5-ef06-40b3-aabb-fb89b45a8f14)
4. Retrieve DHCP reservation information on the routers.
   ![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/1ede971f-ba5d-4a45-87f5-2cd255774a11)
5. Identify the AP number on the swicth by checking the mac address on the trunk ports.
6. Retreive the ACL configuration.
7. Contruct the IP reservation based on the arp table and the converted VLAN IP:
   ![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/9d5b8b96-840f-4540-bf4c-545c6a03c4dc)
9. Identifies interfaces vlan by the following rules:
![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/66365d98-353a-43d5-83c1-2c06253c928c)

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
8. `ansible-playbook play2.yaml > log`
9. `Ctrl + A + D`
10. `tail -f log` to monitor the process
11. outputs are generated in `output/interface_report.csv` and `output/mac_address_table.txt`


