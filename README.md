本文将引导您将Gandi DNS提供商添加到Synology DDNS服务中。

这是一个原生整合。与每几小时安排一次的任务相比，

优势在于一旦IP发生变化，Synology的DDNS服务就会立即更新它。

因此，NAS的动态IP总是可以随时访问的。而定期更新无法确保这一点。

由于设置部分所需的信息不是标准的，Synology接口中的字段名称不一定与输入匹配。

请按我设置部分提示填写。

安装很简单，您可以使用curl直接下载和编写代码。

安装

使用ssh连接到NAS并切换到root用户：


sudo -s
安装模块：


curl -w "\n" https://web.peifeng.li/gandi_ddns/gandi.php > /usr/syno/bin/ddns/gandi.php
更新文件权限：


chmod 755 /usr/syno/bin/ddns/gandi.php
将其添加到提供商列表中，编辑 /etc/ddns_provider.conf添加服务商。


curl -w "\n" https://web.peifeng.li/gandi_ddns/ddns_provider.conf >> /etc/ddns_provider.conf
注: 自 DSM 7.0 起自定义服务商名称必须以(USER_)前缀开头,

请注意不要修改/etc.defaults/ddns_provider.conf，

修改此文件后每次更新dsm都会被系统更新覆盖修改的文件而丢失配置！

设置



恭喜您！现在新的服务商应该可以在控制面板 -> 外部访问 -> DDNS 中可用。


