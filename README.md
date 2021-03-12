# ansible
1. hosts 
2. [test_ansible]
ansible-slave1
ansible-slave2
3. ansible -m shell -a "apt update" all
4. ansible -m shell -a "apt install apache2" all
5. ansible -m apt -a "name=vsftpd state=latest" all
6. ansible -m apt -a "name=nano state=latest" all
7. 
