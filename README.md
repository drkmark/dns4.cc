# dns4.cc
*crew operates a free, independent "network" of 9 DNSCrypt servers spread across the globe to keep your surfing safe and secure.*
*****************************

Personally, we strongly believe in freedom and the fundamental human right to remain anonymous if you wish.

Respecting this fact, all dns4.cc resolvers & anonymizing relays were, are, and always will be:

- **PUBLIC & FREE TO USE**
- **SECURED BY DNSSEC**
- **NON-BLOCKING**
- **NON-LOGGING**
- **NON-FILTERED**

All servers would be used as DNSCrypt public resolvers and/or anonymizing relays. 

**How to :checkered_flag:**

To start using our network simply add the lists of dns4.cc servers and anonymization relays to your `dnscrypt-proxy.toml` config, restart the service and enjoy. 

> Right, we boldly assume that you already have dnscrypt-proxy installed on your :computer: and/or :iphone:. :wink:
> If not, visit the [dnscrypt-proxy repo](https://github.com/DNSCrypt/dnscrypt-proxy) for more details and return back when you are done. Theory and other useful info can be found at the [DNSCrypt website](https://dnscrypt.info/).


It's easy as:

1. Either download dns4.cc repository as ZIP or clone dns4.cc repository to anywhere like 
    ```
    git https://git clone https://github.com/drkmark/dns4.cc.git
    ```
and copy all the files to dnscrypt-proxy working directory (i.e. /opt/dnscrypt-proxy/)
    

2. In `[sources]` section of your `dnscrypt-proxy.toml` configuration file you should add something like:

    a. dns4.cc public resolvers

    ```
    [sources.'dns4.cc-resolvers.md']
        urls = ['https://raw.githubusercontent.com/drkmark/dns4.cc/main/dns4.cc-resolvers.md']
        cache_file = 'dns4.cc-resolvers.md'
        minisign_key = 'OUR-PUBLIC-MINISIGN-KEY-GOES-HERE'
        refresh_delay = 72
    ```

    b. dns4.cc anonymizing relays

```
    [sources.'dns4.cc-relays.md']
        urls = ['https://raw.githubusercontent.com/drkmark/dns4.cc/main/dns4.cc-relays.md']
        cache_file = 'dns4.cc-relays.md'
        minisign_key = 'OUR-PUBLIC-MINISIGN-KEY-GOES-HERE'
        refresh_delay = 72
```

3. In `[anonymized_dns]` section then add routes as needed, i.e. (or as you wish):

```    
    routes = [
        { server_name='dns4.cc-us-ca-ipv4', via=['anon-dns4.cc-us-ny-ipv4'], via=['anon-dns4.cc-us-tx-ipv4'] },
        { server_name='dns4.cc-vn-ipv6', via=['anon-dns4.cc-hk-ipv6'], via=['anon-dns4.cz-ipv6'] },
        .....
        ]
```
Btw. it's not necessary to be "superanonymized" over more than 1-2 relays, as the latency would increase dramatically.
Just check and play with routes to test the latency, e.g. with [DNS leak script](https://github.com/macvk/dnsleaktest/blob/master/dnsleaktest.sh) from [@macvk](https://github.com/macvk).

Read "/your/dncrypt-proxy/working-directory/"`example-dnscrypt-proxy.toml` for proper settings!


- [list of dns4.cc public resolvers](https://raw.githubusercontent.com/drkmark/dns4.cc/main/dns4.cc-resolvers.md)
- [list of dns4.cc anonymization relays](https://raw.githubusercontent.com/drkmark/dns4.cc/main/dns4.cc-relays.md)

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

©2024 darkmark & dns4.cc crew
