#####1. buy a VPS and set up  
The Japan VPS will be better than USA's, however the comunicate will be easier between us and the one can talk in English  
USA Linode https://www.linode.com/  
Japan Conoha https://www.conoha.jp/  

#####2. install shadowsocks (Debian/Ubuntu)  
`apt-get install python-pip  `   
`pip install shadowsocks `

**my shadowsocks.json file**
<pre>

#multiple users
{
   "server":"45.79.153.XX",
   "port_password": {
        "8381": "XXX",
        "8382": "XXX",
        "8383": "XXX",
        "8384": "XXX",
        "8385": "XXX"
    },
   "local_address": "127.0.0.1",
   "local_port":1080,
   "timeout":300,
   "method":"aes-256-cfb",
   "fast_open": false
}

#single user
{ 
   "server":"45.79.153.XX", 
   "server_port":25X, 
   "local_address": "127.0.0.1", 
   "local_port":1080, 
   "password":"mypassword",
    "timeout":300, 
   "method":"aes-256-cfb", 
   "fast_open": false } 
   
</pre>

#####3. start shadowsocks  
**Start**   
`ssserver -c /etc/shadowsocks.json -d start`  
**Stop**   
`ssserver -c /etc/shadowsocks.json -d stop`  
**monitor**  
`netstat -natulp | egrep 838[1-5] | grep -E "tcp.*ESTABLISHED" | awk '{print $4, $5}' | cut -d: -f2 | sort -u `

**Multiple shadowsocks.** *i.e. IPV4 & IPV6*  
`ssserver -c your-path-to-config4.json -d start --pid-file ss1.pid`   
`ssserver -c your-path-to-config6.json -d start --pid-file ss2.pid`

#####4. Install APP on MAC, Andriod  
**For all Clients Mac, Win & Linux**  
https://shadowsocks.org/en/download/clients.html  
**Andriod**  
google play  
**iOS**  
App Store  

#####useful source:  
**master one:**   
http://blog.chinaunix.net/uid-25530360-id-5595974.html   
**multiple IP**:   
https://www.6zou.net/tech/shadowsocks-multiple-ips-outbound-with-iptables-how-to.html  
http://jinke.me/2015/12/20/shadowshocks.html
 
