coredns study
===

The containers of core-dns are up with fixed ips
it is to make them available to each other.
And it make ease run in dafault dns port (53) 
without conflic with another service

**primary** to *example.com*
20.5.0.2

**secondary** to *exerciciosresolvidos.net*
20.5.0.2



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