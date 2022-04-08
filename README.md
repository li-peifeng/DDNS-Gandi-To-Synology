# 添加 Gandi LiveDNS 到 Synology NAS

此项目旨在为使用Gandi.net域名注册商的 Synology NAS 用户提供动态 DNS 功能。它基于LiveDNS RESTful API。

# Installation

1. 添加 python3 到 Synology。
2. 复制脚本到 `/usr/local/bin/gandi_ddns.py` 并添加运行权限。
```
$ sudo curl -o /usr/local/bin/gandi_ddns.py https://raw.githubusercontent.com/li-peifeng/gandi-ddns-synology/main/gandi_ddns.py
$ sudo chmod +x /usr/local/bin/gandi_ddns.py
```

3. 编辑 `/etc/ddns_provider.conf` 添加服务商:

```
[USER_Gandi]
        modulepath=/usr/local/bin/gandi_ddns.py
        queryurl=Gandi
```
> NOTE: the provide name must start with **`USER_`** prefix (since DSM 7.0)

Now on the new provider should be available under `Control Panel -> External Access -> DDNS`

## Configuration

You need to provide the following configuration parameters:

1. FQDN of the host
1. Username, which is ignored
1. Gandy API key

## License

This work is published under [public domain](https://creativecommons.org/licenses/publicdomain/) license.

[1]: https://api.gandi.net/docs/livedns/
