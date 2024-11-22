# My Note

## Inventory

### Check inventory
    ansible-inventory -i inventories/01.yaml  --list 
### Ping it
    ansible server -m ping -i inventories/01.yaml 

### Run
    ansible-playbook -i inventories/01.yaml playbook.yaml -v

# Ad hoc commands
## Manage files and directories
### Get information about a file 
    ansible multi -m stat -a "path=/etc/environment"
### Copy a file to the servers
    ansible multi -m copy -a "src=/etc/hosts dest=/tmp/hosts"
### Retrieve a file from the servers
    ansible multi -b -m fetch -a "src=/etc/hosts dest=/tmp"
