**1.** Command only lists directories in the current path: `ls -d */`
 
	  ls -d */.
**2.** To kill detached screen sessions
	  
	  #To kill one detached session
	  screen -X -S [session # you want to kill] quit
	  #To kill a bacth of sessions
	  screen -ls | grep "^123" | cut -d. -f1 | awk '{print $1}' | xargs kill
	  screen -ls | awk '{print $1}' | grep "^123" | awk '{printf("screen -S %s -p 0 -X quit\n",$0)}' >kill.log
	  
**3** Sed    
	
	#TAB invoke <TAB> by hitting Control+v followed by the TAB key. This may alternatively be achieved by hitting Control+v followd by Control+i,i
	
**4** Order lines based on their duplicated time    
	
	sort input.txt | unique -c | sort -rn | cut -c 9-
	#unique -c make statistic among duplicated time of each line
	#sort -rn recognize the number, and order them (-r , in decreasing order)
	#cut -c 9- , lenght of dupiclated number account for 8 charactor, thiscould get >= 9th charactors     
**5** run commands lines via seperate screen sessions and track their status

	split -l 1 comands_per_line.sh tem 
	find  tem* | xargs -n 1 screen -d -m sh
	while screen -ls | grep -q "ThePrefixOrSuffix"
	do      
	        sleep 1m
	done
	rm tem*     
**6** re-name a buntch of files with a two column file (old_ID\tNew)
	
	while read -r old new 
	do
        arr=( ${old}_*.gz )
        if (( ${#arr[@]}==2 ))
        then
                [[ ${arr[0]} =~ ([1-2]).clean.fq.gz$ ]]
                echo ${arr[0]}
                echo ${new}_${BASH_REMATCH[1]}.clean.fq.gz
                mv ${arr[0]} ${new}_${BASH_REMATCH[1]}.clean.fq.gz

                [[ ${arr[1]} =~ ([1-2]).clean.fq.gz$ ]]
                echo ${arr[1]}
                echo ${new}_${BASH_REMATCH[1]}.clean.fq.gz
                mv ${arr[1]} ${new}_${BASH_REMATCH[1]}.clean.fq.gz
                #mv ${arr[0]} $new
        else
                echo "Error: not two files found for sample $old: ${arr[@]}"
        fi  
	done< IDs.txt    
	
	

