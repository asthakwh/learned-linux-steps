
* `locate`
* `find`
* `grep`
* `which`

If `locate` is not installed, do so with

        sudo apt install mlocate
        locate access.log

find command searches down through a directory structure looking for files which match some criteria - which could be name, but also size, or when last updated

	find /var -name access.log
	find /home -mtime -3
take longer than `locate` did because they search through the filesystem directly rather from an index

 to search for text within a specific file

    grep -R -i "PermitRootLogin" /etc/*

this only works on plain text files


## RESOURCES

* [25 find command examples...](https://www.linuxtechi.com/25-find-command-examples-for-linux-beginners/)