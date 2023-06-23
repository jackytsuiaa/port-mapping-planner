This is a script targeting the stores of Eastern Banner - CTR, Party City, PartSource, Petroleum

1. Retrieve the interfaces status, description and their mac address on the network devices.
2. Perfrom sanity check on the Dealer Lan trunk ports by scanning the interface configuration.
3. Distinguish the primary and secondary IP address on the Dealer network interface.
4. Retrieve DHCP reservation information on the routers.
5. Identify the AP number on the swicth by checking the mac address on the trunk ports.
6. Retreive the ACL configuration.
7. Contruct the IP reservation based on the arp table and the converted VLAN IP.
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
8. `ansible-playbook play0.yaml > log`
9. `Ctrl + A + D`
10. `tail -f log` to monitor the process
11. outputs are generated in `output/`


