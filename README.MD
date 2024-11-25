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
    ansible all -m stat -a "path=/etc/environment"
### Copy a file to the servers
    ansible all -m copy -a "src=/etc/hosts dest=/tmp/hosts"
### Retrieve a file from the servers
    ansible all -b -m fetch -a "src=/etc/hosts dest=/tmp"
### Create directortes and files
    ansible all -m file -a "dest=/tmp/test mode=644 state=directory"
    # symlink
    ansible all -m file -a "src=/src/file dest=/dest/symlink state=link"

### Delete directories and files
    ansible all -m file -a "dest=/tmp/test state=absent"

### Run opeartions in the background
    ansible all -b -B 3600 -P 0 -a "dnf -y update"
    ansible all -b -m async_status -a "jid=169825235950.3572"

## Package
    ansible app -b -m package -a "name=git state=present"
    
    ansible app -b -m git -a "repo=git://example.com/path/to/repo.git dest=/opt/myapp update=yes version=1.2.4"

