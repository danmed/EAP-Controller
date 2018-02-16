[![logo](https://i0.wp.com/homesecurity1st.co.za/wp-content/uploads/2017/02/TP-LINK_logo-300x130-1.jpg?fit=300%2C130&ssl=1)](https://www.tp-link.com/common/Spotlight/EAP_controller.html)

TP-Link EAP Controller
==========================


EAP Controller - https://www.tp-link.com/common/Spotlight/EAP_controller.html



Running on the latest Phusion release (ubuntu 16.04), with EAP Controller v2.5.3


**Pull image**

```
docker pull mace/EAP-Controller
```

**Run container**

```
docker run -d --net="host" --privileged --name=<container name> -v <path for eap config files>:/config -v /etc/localtime:/etc/localtime:ro mace/eap-controller
```
Please replace all user variables in the above command defined by <> with the correct values.
Use --net="host" or --net="macvlan0"

**Web-UI**

```
https://<host ip>:8088
```


**Example**

```
docker run -d --net="host"  --privileged --name=eapcontroller -v /mylocal/directory/fordata:/config -v /etc/localtime:/etc/localtime:ro mace/eapcontroller
```


**Additional notes**


* The owner of the config directory needs sufficent permissions (UUID 99 / GID 100). (For manual configs, backups etc on the host system)
* Should be run with network "host" or "macvlan", so it can find the AP´s
* Username and password will be linked to controller (if you restore a backup this will only restore AP,SSID,etc... settings, not the base controller username/pass)
* Always make an backup of your settings before a new release "EAP controller version"(for a reinstall with same version it´s not necessary)

**Change notes**

* 2018.02.16
Initial release