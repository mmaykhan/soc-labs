\# Mini-SOC in a box - Week 1: Build the lab and deploy Wazuh



\## Overview

Short description of LabShop and what was built.



\## Versions

\- Wazuh: 4.14.7 (manager, indexer, dashboard, agents)

\- Docker Engine / Compose: (paste `docker --version`, `docker compose version`)

\- Windows evaluation image expires on: YYYY-MM-DD



\## Architecture

See `architecture/addresses.md` and `architecture/lab-diagram.png`.



\## Start / stop the whole lab (correct order)

Start: 1) siem-host  2) wait for Docker stack (`sudo docker ps`)  3) ubuntu-web  4) win-client

Stop: 1) win-client  2) ubuntu-web  3) `sudo docker compose stop` in \~/wazuh-docker/single-node  4) siem-host

Never run `docker compose down -v` (it deletes data).



\## Verification: five known events (V1)

| # | Event | Rule description | Level | Screenshot |

|---|---|---|---|---|

| 1 | Failed SSH login | syslog: User missed the password more than one time | 10 | evidence/v1-1-ssh.png |

| 2 | sudo command | (fill in) | (fill in) | evidence/v1-2-sudo.png |

| 3 | New local user | (fill in) | (fill in) | evidence/v1-3-adduser.png |

| 4 | Program started (Sysmon) | (fill in) | (fill in) | evidence/v1-4-sysmon.png |

| 5 | Failed Windows logon | (fill in) | (fill in) | evidence/v1-5-4625.png |



\## Event path (V2)

1\. Event happens on the endpoint (log line / Windows event / Sysmon event).

2\. Wazuh agent reads it and sends it to the manager (port 1514).

3\. Manager decodes it and matches rules, producing an alert.

4\. Alert is forwarded (Filebeat) to the indexer, which stores it.

5\. Dashboard queries the indexer and shows the alert.



\## Memory usage (W5)

| Container | Idle memory |

|---|---|

| wazuh.manager | (fill in) |

| wazuh.indexer | (fill in) |

| wazuh.dashboard | (fill in) |



\## Persistence test (W4)

What I did and what I observed after restart and reboot: (fill in)



\## Security

No passwords, keys or certificates are committed. See `.gitignore`.

