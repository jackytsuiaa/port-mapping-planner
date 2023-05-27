This is a script targeting the stores of Western Banner.

It contains 2 parts.

Play1 - Crawling from a seed switch in each store recursively by reaching to their CDP neighbor, extract the device's information such as Banner, Store, Hostname, IP Address, Model, Serial Number, Stacked Number, Stacked Serial Number, Connection status and catches the Error Message if the connection is fail. The full inventory list is output in csv format.
![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/de6ddca6-d57a-4816-b39e-6c61e3374126)

play2 - Retrieve the interfaces status and their mac address on the network devices, and identify their vlan convertion by the following rules: 
![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/2b45ef62-f6cb-46c8-829a-d3a100c2690b)


To run play 1
1. `cd port-mapping-planner/western-banner/`
2. `cp group_vars/all-copy.yaml group_vars/all.yaml`
3. Configure the username and password in group_vars/all.yaml
4. Make sure the targeted seed switch is in inventory/hosts. Others can be commented out or removed.
5. `rm log1`
6. Create a screen `sreen`
7. `ansible-playbook play1.yaml -i inventory/hosts > log1`
8. `Ctrl + A + D`
9. `tail -f log1` to monitor the process
10. Output is in `output/switch_inventory.csv`
11. Failed switch is captured in `error.log`
12. `inventory/updated_hosts` is generated for play2

To run play 2
1. delete log2 in the original directory
2. make sure the targeted switch is in `inventory/updated_hosts`. you can comment out others. 
3. create a screen `sreen`
4. `ansible-playbook play2.yaml -i inventory/updated_hosts > log2`
5. `Ctrl + A + D`
6. `tail -f log2` to monitor the process
7. it takes ~2 days for all hosts
8. output is in `output/interface_report.csv` and `output/mac_address_table.txt`


