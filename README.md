# AAP Lab Configuration - kvmhost

## Architecture
- **Host IP:** 192.168.1.170
- **HAProxy IP:** 192.168.1.181
- **DNS Server:** 192.168.1.170

## Services
| Service | External URL | Internal Port |
|---|---|---|
| Automation Controller | https://192.168.1.181:444 | 8445 |
| Automation Hub | https://192.168.1.181:445 | 8444 |

## Port Mapping
| HAProxy External | Internal | Service |
|---|---|---|
| 192.168.1.181:444 | 192.168.1.170:8445 | Controller HTTPS |
| 192.168.1.181:445 | 192.168.1.170:8444 | Hub HTTPS |
| 192.168.1.181:81  | 192.168.1.170:8081 | Controller HTTP |
| 192.168.1.181:82  | 192.168.1.170:8082 | Hub HTTP |

## Notes
- nginx controller listens on 8445 (not default 8443, conflicts with k3s/ArgoCD haproxy frontend)
- nginx hub listens on 8444
- Traefik (k3s) owns port 443 on 192.168.1.170
- awx-daphne and awx-uwsgi managed by supervisord
