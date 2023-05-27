This is the script targeting the stores of Western Banner.

It contains 2 parts.

Play1
Crawling from a seed switch in each store recursively by reaching to the CDP neighbor. It extracts the device's Banner, Store, Hostname, IP Address, Model, Serial Number, Stacked Number, Stacked Serial Number, Connection and Error Message in csv format as an output of a full inventory list.

play2 - Get interface list with vlan convertion from Cisco to Juniper


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


