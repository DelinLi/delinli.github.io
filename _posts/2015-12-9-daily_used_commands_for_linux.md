###Daily Used Commands for Linux

*1.* Check the CPU number: 

	cat /proc/cpuinfo |grep "processor"|sort -u|wc -l

*2.* Add a user account named `DL`
	
	useradd -d /home/DL -m DL -s /bin/sh -g Bio -G adm -p changeyourpw

*3.* only list the foders/folders with `ls`
	
	ls -F|grep /$ | grep ^Geno  # -->only list the foders
	ls -F | grep "[^/]$" 		# --> will only list the files
	
*4.* 