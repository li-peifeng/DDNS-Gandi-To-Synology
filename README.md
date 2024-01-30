## 安装说明
# 原apikey已经弃用，请使用PAT（Personal Access Token）！
1. ssh 连接到nas
2. 切换到root: `sudo -s`
3. 安装模块: 
   `curl -w "\n" https://raw.githubusercontent.com/li-peifeng/gandi-ddns-synology/main/gandi.php > /usr/syno/bin/ddns/gandi.php`
4. 设置权限: `chmod 755 /usr/syno/bin/ddns/gandi.php`
5. 添加到服务商菜单: `curl -w "\n" https://raw.githubusercontent.com/li-peifeng/gandi-ddns-synology/main/ddns_provider.conf >> /etc.defaults/ddns_provider.conf`
