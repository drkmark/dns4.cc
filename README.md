# dns4.cc
operates independent network of 9 DNSCrypt servers to keep your browsing safe and secure. 

all our servers are **public, dnssec capable, non-blocking, non-logging and non-filtered** and work like public resoivers and anonymization relays. 


to start using our network simply add the lists of dns4.cc servers and anonymization relays into your dnscrypt-proxy.toml and enjoy.

in `[sources]` section of your `dnscrypt-proxy.toml` configuration file you should add something like:

1. dns4.cc public resolvers

```
    [sources.'dns4.cc-resolvers.md']
        urls = ['
        \']
        cache_file = 'dns4.cc-resolvers.md'
        minisign_key = 'RWQmCQci7XkPir2RcxzcMLtvRJvpxrkKyvovMky2Nn6bWzsGWchGOTS9'
        refresh_delay = 72
```

2. dns4.cc anonymization relays

```
    [sources.'dns4.cc-relays.md']
        urls = ['https://raw.githubusercontent.com/drkmark/dns4.cc/main/dns4.cc-relays.md']
        cache_file = 'dns4.cc-relays.md'
        minisign_key = 'RWQmCQci7XkPir2RcxzcMLtvRJvpxrkKyvovMky2Nn6bWzsGWchGOTS9'
        refresh_delay = 72
```

in `[anonymized_dns]` section then add routes as needed, i.e. (or as you wish)

    routes = [
        { server_name='dns4.cc-us-ca-ipv4', via=['anon-dns4.cc-us-ny-ipv4'], via=['anon-dns4.cc-us-tx-ipv4'] },
        { server_name='dns4.cc-vn-ipv6', via=['anon-dns4.cc-hk-ipv6'], via=['anon-dns4.cz-ipv6'] },
        .....
        ]

**read example-dnscrypt-proxy.toml for proper settings!**

- [list of our DNSCrypt public resolvers](https://raw.githubusercontent.com/drkmark/dns4.cc/main/dns4.cc-resolvers.md)
- [list of our DNSCrypt anonymization relays](https://raw.githubusercontent.com/drkmark/dns4.cc/main/dns4.cc-relays.md)

********************

DNS servers locations as of May 2024:

### US
 - San Jose, CA
 - Dallas, TX
 - Buffalo, NY

### Europe
 - Coventry, UK
 - Frankfurt Am Main, Germany
 - Budweis, Czechia
 - Bratislava, Slovakia

### Asia/Pacific
 - Ho Chi Minh City, Vietnam
 - Hong Kong, China


********************

...and that's all, folks. have a good time!

dns4.cc team
