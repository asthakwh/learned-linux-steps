Show IP addresses configuration

        ip a
        ifconfig
        ifconfig all
        ip addr show

`sudo apt install net-tools -y` list internet port opened by a process

        netstat
        netstat -tln #show open TCP
        
`sudo apt install network-manager -y` insert more than one nameserver as backup
        
        
        systemctl stop NetworkManager.service
        systemctl disable NetworkManager.service
        systemctl status network 
        systemctl restart network

        nmtui

if change in ip address 
        
        ip link set eth0 down
`ip addr add 192.168.0.2/24 dev eth0` Assign IP 192.168.0.2/24 to interface eth0
`ip link set eth0 up` Restart interface eth0

configure DNS servers entry

        /etc/resolv.conf

debug: insert more than one nameserver as backup 


`ss` - this, "socket status", is a standard utility - replacing the older `netstat`

        sudo ss -ltp

`nmap` - this "port scanner" won't normally be installed by default

        nmap localhost

define tables containing chains of rules for the treatment of packets

        yum -y install iptables-services
        sudo iptables -L #utility to manage firewall

if no policy 

        sudo apt install ufw
        sudo ufw allow ssh #allow SSH  and also = deny” ssh, or you’ll lose all contact with your server
        sudo ufw deny http  # disallow HTTP
        sudo ufw enable
        sudo iptables -L # check again

        sudo ufw allow http
        sudo ufw enable

Firewall: managed by Kernel

        firewall-cmd --list-all
        #services - allowed to use interface
        #ports - allowed to use interface

`firewalld` is a service that use iptables to manage firewalls rules

`firewall-cmd` is the command to manage `firewalld`

        firewall-cmd --reload # to reload configuration
        firewall-cmd --add-port 8000/tcp
        sudo systemctl stop firewalld
        systemctl disable firewalld

systemctl enable iptables

to Show route
`ip route show` or `route -n`

NTP : on 

A local server must use an NTP client to get the correct time from a remote NTP server

        sudo yum -y install chrony   # [On CentOS/RHEL]
        sudo apt install chrony      # [On Debian/Ubuntu]
        sudo dnf -y install chrony   # [On Fedora 22+]

NTP service `chrony` is a flexible Network Time Protocol implementation
        
        sudo nano /etc/chrony.conf # config file

check status of chronyd

        sudo systemctl status chronyd      [On SystemD]
        /etc/init.d/chronyd status    [On Init]
        sudo systemctl stop chronyd
        sudo systemctl disable chronyd
        sudo systemctl enable chronyd
        sudo systemctl start chronyd

 and sync the system clock with NTP servers
 
        sudo yum install -y ntp
        sudo vi /etc/ntp.conf

give servers entry

        #server 192.168.1.100 iburst
        #server ip-pool iburst

        sudo systemctl enable ntpd
        sudo systemctl start ntpd
        systemctl status ntpd

`ntpq -p` check current status of synchronization
also allow from firewall

        sudo firewall-cmd --permanent --add-service=ntp
        sudo firewall-cmd --reload

verify `timedatectl` or `date`


