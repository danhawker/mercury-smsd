# mercury-smsd
SMSD config on Mercury

Mercury is a small embedded [Foxboard LX832](http://www.acmesystems.it/FOXLX) from Acme Systems that I use to monitor power at my cottage and alert me to power outages and other small things.

For SMS functionality it uses [smstools3](http://smstools3.kekekasvi.com/) which provides a series of SMS utilities and tools that includes a lightweight SMS Daemon for sending/receiving messages from an attached modem. [smstools3](http://smstools3.kekekasvi.com/) was chosen because the Foxboard runs a **really** old version of OpenWRT, which is unfortunately the newest OS available for the now long discontinued board, and smstools3 is the only SMS package available. The choice was pretty simple.

## Initscript
The initscript `smsd.init` is OpenWRT inspired and CrisOS focused, hence leverages a few standardised settings that are only useful to that paticular distro.

To use the initscript it should be installed in `/etc/init.d`.
```
root@host:~# cp smsd.init /etc/init.d/smsd
```
    
To enable SMSD to start at boot, enable it
```
root@host:~# /etc/init.d/smsd enable
```

To start/stop/restart SMSD 
````
root@host:~# /etc/init.d/smsd start
root@host:~# /etc/init.d/smsd stop
root@host:~# /etc/init.d/smsd restart
```

## Configuration
Configuration is held within `smsd.conf` which should be installed inside `/etc`.
```
root@host:~# cp smsd.conf /etc/smsd.conf
```
