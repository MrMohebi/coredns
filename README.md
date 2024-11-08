## Example config:
```
.:5322 {

    hosts /etc/hosts-ir {
        reload 500ms
        fallthrough
    }

    iran_resolver {
        dns-to-check 78.157.42.101:53 10.202.10.202:53

        sanction-search .403. electro
        ban-search 10.10.34.35

        sanction-hosts-file /etc/hosts-sanction
        ban-hosts-file /etc/hosts-ban

        result-hosts-file /etc/hosts-ir

        sanction-dest-server-ips 10.10.10.10
        ban-dest-server-ips 20.20.20.20

        sanction-buffer-size 10
        ban-buffer-size 10
    }

    forward . 8.8.8.8 {
        expire 0
    }

    log
    errors
}

```

## Run:
``` bash
$ git clone 
$ make
$ go generate
$ go get github.com/MrMohebi/coredns_iran_resolver
$ go build
$ ./coredns -conf ./coredns.config # as root
```