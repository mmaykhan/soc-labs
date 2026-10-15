\# LabShop Week 1 address table



| Machine | Role | OS | RAM | vCPU | Disk | IP (host-only) | Adapters |

|---|---|---|---|---|---|---|---|

| siem-host | Wazuh in Docker | Ubuntu Server LTS | 16 GB | 4 | 250 GB | 10.10.10.10 | Host-only + NAT |

| ubuntu-web | Linux endpoint, Apache | Ubuntu Server LTS | 2 GB | 2 | 40 GB | 10.10.10.20 | Host-only |

| win-client | Windows endpoint, Sysmon | Windows 10 | 4 GB | 2 | 80 GB | 10.10.10.30 | Host-only |

