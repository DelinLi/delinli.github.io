**1.** Command only lists directories in the current path: `ls -d */`
 
	  ls -d */.
**2.** To kill detached screen sessions
	  
	  #To kill one detached session
	  screen -X -S [session # you want to kill] quit
	  #To kill a bacth of sessions
	  screen -ls | grep "data2bio" | cut -d. -f1 | awk '{print $1}' | xargs kill
	  
**3** Sed    
	
	#TAB invoke <TAB> by hitting Control+v followed by the TAB key. This may alternatively be achieved by hitting Control+v followd by Control+i,i
	
**4** Order lines based on their duplicated time    
	
	sort input.txt | unique -c | sort -rn | cut -c 9-
	#unique -c make statistic among duplicated time of each line
	#sort -rn recognize the number, and order them (-r , in decreasing order)
	#cut -c 9- , lenght of dupiclated number account for 8 charactor, thiscould get >= 9th charactors