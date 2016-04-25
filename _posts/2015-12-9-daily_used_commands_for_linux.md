###Daily Used Commands for Linux

*1.* Check the CPU number: 

	cat /proc/cpuinfo |grep "processor"|sort -u|wc -l

*2.* Add a user account named `DL`
	
	useradd -d /home/DL -m DL -s /bin/sh -g Bio -G adm -p changeyourpw

*3.* only list the foders/folders with `ls`
	
	ls -F|grep /$ | grep ^Geno  # -->only list the foders
	ls -F | grep "[^/]$" 		# --> will only list the files
	
*4.* Split a centence into items
<pre>
#!/bin/bash

str="hello,world,i,like,you,babalala"
arr=(${str//,/ })

for i in ${arr[@]}
do
    echo $i
done
</pre>

*5.* FASTQ to FASTA format

	zcat input_file.fastq.gz | awk 'NR%4==1{printf ">%s\n", substr($0,2)}NR%4==2{print}' > output_file.fa