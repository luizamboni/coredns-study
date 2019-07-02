coredns study
===

see:

https://dev.to/robbmanes/running-coredns-as-a-dns-server-in-a-container-1d0

```bash
  nslookup google.com localhost -port=52
```

obs.: the port must be diff of default (53), becouse docker daemon already up a embeded dns server
in this port