---
layout:  null
title:  Keep running of a process via Auto scan
---
####I'm assuming you are using a Mac or linux device. Strategy below will not work under a PC with win systems

**Firstly**, create a script ,like `Running.Check.sh`,with either method 1 or method 2. They both work for make sure the tunnel of socks5 is running.

###Method 1
<pre>
return=`ps -u Data2Bio | grep "SCREEN -d -m ssh -C2qTnN -[D] 8080 username@**.***.**.*"`
echo $return
if [ ${#return} -eq 0 ] 
then
        screen -d -m ssh  -C2qTnN -D 8080  username@**.***.**.*
fi
</pre>

###Method 2
<pre>
Status=$(ps -A | grep -w "C2qTnN" | grep "ssh")
echo $Status
if ! [ -n "$Status" ]
then
        ssh -C2qTnN -D 8080 username@**.***.**.*
fi
</pre>

**Secondly**, run this script every one minutes with **crontab**. Open the crontab via `crontab -e` to add sentence below, save and exit. 
open
<pre>
*/1 * * * * screen -d -m sh /Users/Delin/Documents/GitHub/Bioinfo_Delin/Scripts_Tools/Running.Check.sh
</pre>

You are all set to let the socks5 tunnel open once you can access your server.


