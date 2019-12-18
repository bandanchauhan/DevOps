Ad-Hoc commands are one-liner ansible commands that performs one task on the target host. 
It allows you to execute simpleone-line task against one or group of hosts defined on the inventory file configuration.


how to run ansible ad-hoc commands ( default inventory ) with uid/pwd

	ansible all -m setup -u username -k 
        ansible qa -m ping -u username -k
        ansible dev -m shell -a "free -m" -u username -k
        ansible iat -m copy -a "src=/tmp/naresh.txt dest=/tmp" -u username -k 
        ansible prod -m file -a "path=/tmp/helousername.txt state=touch" -u username -k

how to run ansible ad-hoc with custom inventory & uid/pwd

	ansible all -i /path/to/inventory -u username -k
        ansible dev -i /path/to/inventory -m copy -a "src=/tmp/new.txt dest=/tmp" -u username -k

how to run ansible ad-hoc with super user (root) with uid/pwd

        ansible all -i /path/to/inventory -b -u username -k -K
        ansible dev -i /path/to/inventory -m copy -a "src=/tmp/new.txt dest=/tmp" -b -u username -k -K
