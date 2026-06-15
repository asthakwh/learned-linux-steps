
use:
configure set of scheduled tasks is key to keeping your server running well

path:
        /etc/crontab

        crontab -e
        #m h dom mon dow user  command
list out your user crontab entry 

        crontab -l
 to see what’s actually scheduled.

        ls /etc/cron.*

        ls  /etc/cron.daily