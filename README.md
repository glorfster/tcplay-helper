# tcplay-helper
## Using with the `pam_mount`:
* add `/etc/pam.d/mount`
```
auth            optional        pam_mount.so
password        optional        pam_mount.so
session         optional        pam_mount.so
```
* `/etc/pam.d/system-local-login` and `/etc/pam.d/system-remote-login`
```
auth		include		mount
password		include		mount
session		include		mount
```
* `/etc/security/pam_mount.conf.xml`
```xml
<cryptmount>bash -c "/usr/bin/tcplay-helper open '%(VOLUME)' '%(MNTPT)'"</cryptmount>
<cryptumount>bash -c "/usr/bin/tcplay-helper close '%(MNTPT)'"</cryptumount>
```
