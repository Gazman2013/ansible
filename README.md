# ansible
1. hosts 
2. [test_ansible]
ansible-slave1
ansible-slave2
3. ansible -m shell -a "apt update" all
4. ansible -m shell -a "apt install apache2" all
5. ansible -m shell -a "systemctl status apache2" all
6. Mar 12 08:44:58 ansible-slave1 systemd[1]: Starting The Apache HTTP Server...
7. Mar 12 08:44:58 ansible-slave2 systemd[1]: Starting The Apache HTTP Server..
8. ansible -m apt -a "name=vsftpd state=latest" all
9. Mar 12 08:47:47 ansible-slave1 systemd[1]: Started vsftpd FTP server.
10. Mar 12 08:47:47 ansible-slave2 systemd[1]: Started vsftpd FTP server. 
12. ansible -m apt -a "name=nano state=latest" all
13. ansible all -m group -a "name=students" 
14. ansible -m user -a "name=student groups=students append=yes" all
15. 
