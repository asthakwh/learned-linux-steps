`ss` - this, "socket status", is a standard utility - replacing the older `netstat`

        sudo ss -ltp

`nmap` - this "port scanner" won't normally be installed by default

        nmap localhost

define tables containing chains of rules for the treatment of packets

        sudo iptables -L

if no policy 

        sudo apt install ufw
        sudo ufw allow ssh #allow SSH  and also = deny” ssh, or you’ll lose all contact with your server
        sudo ufw deny http  # disallow HTTP
        sudo ufw enable
        sudo iptables -L # check again

        sudo ufw allow http
        sudo ufw enable