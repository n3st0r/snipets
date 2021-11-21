
Show routing based on DNS name
```
ip route get $(dig +short a google.com|tail -n1)
```