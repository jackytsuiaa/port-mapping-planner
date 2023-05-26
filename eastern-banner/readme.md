This is the scripts targetting to the stores in Eastern Banner.

Note to create a 
Download Vitual Box
Create Ubuntu
sudo passwd root
allow ssh
reboot
port forwarding
sudo apt update
sudo apt install python3-pip

sudo apt install ansible

this project include 2 parts
play1 - get all the switch inventory
play2 - get interface information


to run play 1
1. delete log1 in the original directory
2. create a screen `sreen`
3. `ansible-playbook play1.yaml -i inventory/hosts > log1`
4. `Ctrl + A + D`
5. `tail -f log1` to monitor the process
6. it takes ~2 days for all hosts
7. output is in `output/switch_inventory.csv`
8. failed switch is captured in `error.log`
9. `inventory/updated_hosts` is generated for play2

to run play 2
1. delete log2 in the original directory
2. make sure the targeted switch is in `inventory/updated_hosts`. you can comment out others. 
3. create a screen `sreen`
4. `ansible-playbook play2.yaml -i inventory/updated_hosts > log2`
5. `Ctrl + A + D`
6. `tail -f log2` to monitor the process
7. it takes ~2 days for all hosts
8. output is in `output/interface_report.csv` and `output/mac_address_table.txt`


