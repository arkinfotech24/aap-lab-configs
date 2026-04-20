# AAP Lab Configuration Files

Ansible Automation Platform 2.4 lab setup on a single-node KVM host.

## Environment
- **Host:** kvmhost.lab.local (192.168.1.170)
- **HAProxy:** 192.168.1.181
- **Controller UI:** https://192.168.1.181:444
- **Hub UI:** https://192.168.1.181:445

## Files
- `inventory` - AAP installer inventory (passwords masked)
- `haproxy.cfg` - HAProxy routing configuration
- `automation-controller.nginx.conf` - Nginx controller config
- `automation-hub.nginx.conf` - Nginx hub config
- `kvmhost.lab.local.zone` - DNS zone file
- `lab.local.zone` - DNS zone file
- `home.lab.zone` - DNS zone file

## Notes
- Replace all `CHANGE_ME` values with your actual passwords before running setup
- Replace `YOUR_RH_USERNAME` with your Red Hat registry username
