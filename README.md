# 关于开发
1. 此项目为使用Gandi.net域名注册商的群晖NAS用户提供DDNS功能。
2. 使用Gandi LiveDNS RESTful API。
3. 项目集成到NAS系统DDNS菜单，使用方便。
4. 个人兴趣开发，有问题可以提。
# 1-安装Gandi LiveDNS 到 Synology NAS
1. 添加 python3 到 Synology。
2. 复制脚本 `/usr/local/bin/gandi_ddns.py` 并添加运行权限。
```
$ sudo curl -o /usr/local/bin/gandi_ddns.py https://raw.githubusercontent.com/li-peifeng/gandi-ddns-synology/main/gandi_ddns.py
$ sudo chmod +x /usr/local/bin/gandi_ddns.py
```
3. 编辑 `/etc/ddns_provider.conf` 添加服务商。
> 注: 自 DSM 7.0 起自定义服务商名称必须以(USER_)前缀开头,请注意不要修改`/etc.defaults/ddns_provider.conf`，修改此文件后每次更新dsm都会被系统更新覆盖修改的文件而丢失配置！
```
[USER_Gandi]
  modulepath=/usr/local/bin/gandi_ddns.py
  queryurl=Gandi
```
恭喜您！现在新的服务商应该可以在`控制面板 -> 外部访问 -> DDNS` 中可用。
# 2-配置
您需要提供以下配置参数：
1. 主机FQDN，可使用裸域名或二级域名。
2. 用户名
3. Gandi API 密钥
