coredns study
===

The containers of core-dns are up with fixed ips
it is to make them available to each other.
And it make ease run in dafault dns port (53) 
without conflic with another service

**primary** and **secondary** to *example.com* and *exerciciosresolvidos.net*
- uses **log** plugin
IP: 20.5.0.3
IP: 20.5.0.2

**Examples:** 
Query a fowarded domain
```bash
$ nslookup google.com 20.5.0.2
```

Query a domain where this is Authority
```bash
$ nslookup host.example.com 20.5.0.2
```

Query a specific A record type
```bash
$ nslookup -type=A host.example.com 20.5.0.2
```

Query a specific AAAA record type
```bash
$ nslookup -type=AAAA host.example.com 20.5.0.2
```

Query cname
```bash
$ nslookup alias.example.com 20.5.0.2
```

```bash
$ nslookup alias2.example.com 20.5.0.2
```

**by-host** are configured by a /etc/hosts like file
IP: 20.5.0.3

**auto** 
- uses the auto plugin to load zone files
- uses **ready** plugin that enable a /ready endpoint that inform all plugin chain is ready
- uses **health** plugin too
- uses **loadbalancer** thats change orders o ip registers
IP: 20.5.0.5

Examples:

api endpoint
```bash
$ curl 10.5.0.5:8181/ready
# OK
$ curl 10.5.0.5:8080/health
# OK
```

loadbalancer
```bash
$ nslookup a.bar.example 10.5.0.5
```
