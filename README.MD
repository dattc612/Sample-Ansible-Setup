# My Note

## Inventory

### Check inventory
    ansible-inventory -i inventories/01.yaml  --list 
### Ping it
    ansible server -m ping -i inventories/01.yaml 

### Run
    ansible-playbook -i inventories/01.yaml playbook.yaml -v
