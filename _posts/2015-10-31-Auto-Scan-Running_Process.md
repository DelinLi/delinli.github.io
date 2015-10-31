
###Method1
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
