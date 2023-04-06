# squid_proxy
setup squid proxy ubuntu


## installion

```
sudo apt update
sudo apt upgrade -y
sudo apt install squid
```

## Edit conf file

```
vim /etc/squid/squid.conf
```

apppend these lines in the file to allow only your favorite ips


```
acl allowed_host src 93.167.40.0/36 #change to your public ip
http_access allow allowed_host
```

append these lines to block the web site

```
acl CONNECT method CONNECT
acl block_websites dstdomain .xnxx.com .facebook.com .tiktok.com
http_access deny block_websites
```

## port

```
by default listen port is :
3128
```

## log file

see the log file in 

```
/var/log/squid
```
