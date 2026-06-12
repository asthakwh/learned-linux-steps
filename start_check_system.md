1 = list Files        
        
        ls 

2 = your server did actually fully restart
        uptime

3 = 
        
        free

4 = check disk space        

        df -h
5 = 
uname -a

6 = to switch root user

        sudo -i

7 =  where any use of sudo is logged

        less /var/log/auth.log

8 = filter where sudo used

        grep "sudo" /var/log/auth.log

9 = check current settings

        timedatectl

10 = to edit hostname 
paths:

        /etc/hostname
        /etc/hosts

also:

        sudo hostnamectl set-hostname enter_new_name

11 = 