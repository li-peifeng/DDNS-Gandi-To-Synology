# 添加 Gandi LiveDNS 到 Synology NAS

此项目旨在为使用Gandi.net域名注册商的 Synology NAS 用户提供动态 DNS 功能。它基于LiveDNS RESTful API。

# 安装

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
> 注: 自 DSM 7.0 起服务商名称必须以USER_前缀开头。

现在新的服务商应该可以在`控制面板 -> 外部访问 -> DDNS` 可用。

# 配置

您需要提供以下配置参数：

1.主机FQDN，可使用裸域名或二级域名。

2.用户名

3.Gandi API 密钥
