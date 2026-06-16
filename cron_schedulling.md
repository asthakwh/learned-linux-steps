
use:
configure set of scheduled tasks is key to keeping your server running well

`
┌───────────── Minute (0 - 59)
│ ┌───────────── Hour (0 - 23)
│ │ ┌───────────── Day of Month (1 - 31)
│ │ │ ┌───────────── Month (1 - 12 or Jan-Dec)
│ │ │ │ ┌───────────── Day of Week (0 - 7 or Sun-Sat)
│ │ │ │ │
* * * * * command_to_execute`

path:
        `/etc/crontab`

        crontab -e
        #m h dom mon dow user  command
list out your user crontab entry 

        crontab -l
 to see what’s actually scheduled.

        ls /etc/cron.*

        ls  /etc/cron.daily