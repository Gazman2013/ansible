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
15. ansible-slave1 | CHANGED => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "append": false,
    "changed": true,
    "comment": "",
    "group": 1005,
    "home": "/home/student",
    "move_home": false,
    "name": "student",
    "password": "NOT_LOGGING_PASSWORD",
    "shell": "/bin/sh",
    "state": "present",
    "uid": 1003
}
ansible-slave2 | CHANGED => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "append": false,
    "changed": true,
    "comment": "",
    "group": 1005,
    "home": "/home/student",
    "move_home": false,
    "name": "student",
    "password": "NOT_LOGGING_PASSWORD",
    "shell": "/bin/sh",
    "state": "present",
    "uid": 1003
16. ansible  -m file -a "path=/home/student/test1 state=directory" all
17. ansible  -m file -a "path=/home/student/test1/test2 state=directory" all
18. ansible  -m file -a "path=/home/student/test1/test2/test3 state=directory" all
19. ansible all -m shell -a "ifconfig"
ansible-slave1 | CHANGED | rc=0 >>
ens4: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1460
        inet 10.128.0.27  netmask 255.255.255.255  broadcast 0.0.0.0
        inet6 fe80::4001:aff:fe80:1b  prefixlen 64  scopeid 0x20<link>
        ether 42:01:0a:80:00:1b  txqueuelen 1000  (Ethernet)
        RX packets 82864  bytes 193552148 (193.5 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 82150  bytes 9093025 (9.0 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 4450  bytes 410217 (410.2 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4450  bytes 410217 (410.2 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
20. ansible all -m setup -a '"filter=ansible_all_ipv4_addresses"
22. ansible all -m shell -a "cat /proc/cpuinfo" && ansible all -m shell -a "cat /proc/meminfo" && ansible all -m shell -a "cat /etc/issue" и так далее
23. ansible all -m setup -a "gather_subset=hardware"
24. Про провайдера облака пока не придумал
