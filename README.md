TeamD template for Zabbix
===========================================


Tested on Zabbix Version 3.2

See at [share.zabbix.com](https://share.zabbix.com/operating-systems/teamd-monitoring)

FEATURES
--------
* Monitoring of teamd master and slave interfaces
* Provides alerting on link loss, link loss count, and team state


REQUIREMENTS
------------
* Zabbix server version 3.2
* teamd configured
	* Currently only tested on RHEL7 and CentOS 7
* zabbix account must have sudo permissions to run teamdctl!

INSTALLATION
------------
* Agent
  * Copy __userparameter_teamd.conf__ to __/etc/zabbix/zabbix\_agentd.d/userparameter\_teamd.conf__
  * Restart zabbix_agent
* Server
  * Import template __Template-App-Linux-teamd.xml__ file
  * Add Value Mapping Information

Testing
-------
To test that everything works use the `zabbix_agentd -t` to query the statistics :

```bash
# Discover team interfaces
zabbix_agentd -t "team.discovery"
```

AUTHOR
------
MogiePete

LICENSE
-------
GNU GENERAL PUBLIC LICENSE Version 3, 29 June 2007
