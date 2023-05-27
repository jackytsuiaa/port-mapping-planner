This is a script targeting the stores of Western Banner.

It contains 2 parts.

Play1 - Crawling from a seed switch in each store recursively by reaching to their CDP neighbor while extracting the device's information such as Banner, Store, Hostname, IP Address, Model, Serial Number, Stacked Number, Stacked Serial Number, Connection status and catches the Error Message if the connection is fail. The full inventory list is output in csv format.
![image](https://github.com/jackytsuiaa/port-mapping-planner/assets/98607668/de6ddca6-d57a-4816-b39e-6c61e3374126)

play2 - Get interface list with vlan convertion from Cisco to Juniper It retrieves the interfaces status and their mac address on the network devices, and identifies their vla
n by the following rules: 


To run play 1
1. `cd port-mapping-planner/western-banner/`
2. `rm log1`
3. create a screen `sreen`
4. `ansible-playbook play1.yaml -i inventory/hosts > log1`
5. `Ctrl + A + D`
6. `tail -f log1` to monitor the process
7. output is in `output/switch_inventory.csv`
8. failed switch is captured in `error.log`
9. `inventory/updated_hosts` is generated for play2

To run play 2
1. delete log2 in the original directory
2. make sure the targeted switch is in `inventory/updated_hosts`. you can comment out others. 
3. create a screen `sreen`
4. `ansible-playbook play2.yaml -i inventory/updated_hosts > log2`
5. `Ctrl + A + D`
6. `tail -f log2` to monitor the process
7. it takes ~2 days for all hosts
8. output is in `output/interface_report.csv` and `output/mac_address_table.txt`


