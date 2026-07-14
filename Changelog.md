# Changes to Ubuntu24-CIS-Audit

## 2.0.0 - 2026-07-14 - CIS Ubuntu 24.04 LTS Benchmark v2.0.0 upgrade

- Updated benchmark_version to '2.0.0' and BENCHMARK_VER in run_audit.sh
- vars/CIS.yml: added 78 new v2 toggles; removed 58 retired v1 toggles
- Updated ubtu24cis_ipv6_required default to true and ubtu24cis_time_sync_tool to chrony
- Restructured section 3 sysctl: retired flat cis_3.3 controls; added cis_3.3.1.x (18 IPv4) and cis_3.3.2.x (8 IPv6) dirs
- Restructured section 4: retired nftables (cis_4.3) and iptables (cis_4.4); UFW moved from cis_4.2 to cis_4.1
- Restructured section 6 journald: cis_6.1.1.x renamed to cis_6.1.1.1.x (7 controls)
- Restructured section 6 logging: journal-remote (cis_6.1.2.1.x) removed; rsyslog now at cis_6.1.2.x (10 controls); log access at cis_6.1.3.x
- Added 9 auditd stub tests for 6.2.3.22-30
- Added stubs for sections 1, 2, 5 new v2 controls
- Updated goss.yml directory paths throughout
- Stub tests marked for manual implementation: all new v2 controls

# several fixed Oct Nov 25
alignment
typos
corrected chrony path sources

thanks to @jbruno
#11
#12
#13
#16

## 0.9 - based upon CIS 1.0.0 - Initial
