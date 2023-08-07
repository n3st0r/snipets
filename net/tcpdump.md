# Examples of `tcpdump` network analyzer usage
[README.md - back](../README.md)

```
tcpdump -i eth0 -n port 443
```
* `-i eth` - interface to listen on
* `-n` - do not resolve hostnames, also `-nn` maens do not resolve hostnames and services
* `-v` - verbose, more v, more verbose, example: `-vvv`
* `-w test.pcap` - wrtie output to file `test.pcap`

## find traffic based on packet size
```
tcpdump less 32
tcpdump greater 64
tcpdump <= 128
```

## Usefull examples:

From specific ip and destined for a specific port
```
tcpdump -nnvvS src 192.168.0.13 and dst port 80
```

Non icmp traffic going to a specific ip:
```
tcpdump dst 192.168.0.13 and src net and not icmp
```


## Capture only HTTP packets with verbs GET and POST
Capture GET:
```
tcpdump -s 0 -A -vv 'tcp[((tcp[12:1] & 0xf0) >> 2):4] = 0x47455420'
```
Capture POST:
```
tcpdump -s 0 -A -vv 'tcp[((tcp[12:1] & 0xf0) >> 2):4] = 0x504f5354'
```

Extract HTTP Request URL's:
```
tcpdump -s 0 -v -n -l | egrep -i "POST /|GET /|Host:"
```

Capture Cookies from Server and from Client:
```
tcpdump -nn -A -s0 -l | egrep -i 'Set-Cookie|Host:|Cookie:'
```