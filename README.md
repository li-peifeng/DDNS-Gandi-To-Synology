<p align="center">
  <a href="https://peifeng.li"><img width="184px" alt="logo" src="https://li-peifeng.github.io/isweet/logo.png" />
  </a>
</p>

## 安装说明
> [!CAUTION]
> 原apikey已经弃用，请使用PAT（Personal Access Token）！

### 此脚本默认TTL = 600秒
1. ssh 连接到 nas
2. 切换到 root:
3. ```sudo -s```
6. 安装模块:
7. ```curl -w "\n" https://raw.githubusercontent.com/li-peifeng/DDNS-Gandi-To-Synology/main/gandi.php > /usr/syno/bin/ddns/gandi.php```
8. 设置权限:
9. ```chmod 755 /usr/syno/bin/ddns/gandi.php```
12. 添加到服务商菜单:
13. ```curl -w "\n" https://raw.githubusercontent.com/li-peifeng/DDNS-Gandi-To-Synology/main/ddns_provider.conf >> /etc.defaults/ddns_provider.conf```
16. 配置请参照下图：
![配置参考](https://github.com/li-peifeng/DDNS-Gandi-To-Synology/blob/d939f1e043e1c6ac62b010ad0118e1c83f51242f/IMG_0032.jpeg)
