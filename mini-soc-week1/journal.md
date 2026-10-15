\# Journal



\## 2026-10-14 - Docker permission denied

Tried: ran `docker compose ...` right after adding my user to the docker group.

Failed: "permission denied ... docker.sock".

Fixed: group change needs a new login session; used `sudo` meanwhile.



\## 2026-10-14 - Indexer would not start (cert path "not a directory")

Tried: `docker compose up -d` after the cert generation had failed.

Failed: Docker created the missing cert paths as directories, indexer error "not a directory".

Fixed: `docker compose down -v`, removed the cert folder with sudo, regenerated certs with sudo, started again.



\## 2026-10-14 - Static IPs on host-only network

(what you did, what broke, what fixed it)



\## 2026-10-14 - SSH not available on ubuntu-web

Tried: failed SSH login test. Failed: SSH server missing and host-only has no internet.

Fixed: temporarily re-added NAT, installed openssh-server, removed NAT again, confirmed ping 8.8.8.8 fails.



\## 2026-10-14 - Sysmon event search found nothing

Tried: filtering on notepad. Failed: too narrow filter.

Fixed: searched eventID 1 broadly, then used `cmd.exe /c whoami`.

