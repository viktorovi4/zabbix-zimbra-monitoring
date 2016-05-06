# zabbix-zimbra-monitoring
Monitoring Zimbra services states with zabbix.

###files in repository:
zbx_zimbra_template.xml - template for zimbra monitoring. Import on zabbix server.
zabbix-read-logs.te - module for selinux (if selinux mode is enforcing). Allow zabbix agent to read zimbra log files. Install with "checkmodule -M -m -o zabbix-read-logs.mod zabbix-read-logs.te && semodule_package -m zabbix-read-logs.mod -o zabbix-read-logs.pp && semodule -i zabbix-read-logs.pp"
userparameter_zimbra_monitoring.conf - Config with UserParameter settings. Put it in the /etc/zabbix/zabbix_agentd.d/ directory (or something like this), then include in zabbix agent configuration file ("Include=/etc/zabbix/zabbix_agentd.d/").
zimbra_monitoring.sh - monitoring script.
