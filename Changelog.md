# Changes to Ubuntu24-CIS-Audit

## CIS Benchmark 1.0.0

## October 2026 - QA fixes

- 1.5.2 live ptrace value uses ubtu24cis_ptrace_value
- 1.6.1 banner check handles multi-line banners
- 6.1.3.6 runs only when a remote log server is set
- 6.1.3.7 gated on ubtu24cis_system_is_log_server
- 5.2.3 uses the benchmark logfile check
- 5.4.2.4 accepts a locked root account
- 5.4.2.8 uses the benchmark valid shell check
- 3.3.11 expects accept_ra 0
- 6.1.2.1.2 and 6.1.2.1.3 run only when a remote log server is set
- LICENSE: company name updated to MindPoint Group - A Quantum Sky Company
- 1.1.2.6.4 and 1.1.2.7.3 gated on their own rule toggles
- 1.3.1.4 complain mode test made dash-compatible and corrected
- 1.5.1 to 1.5.3 sysctl and limits regex anchored, conflicting values detected
- 1.6.1 invalid YAML escapes fixed, motd files grep matches literal escapes
- 1.6.4 invalid exec resource replaced, mode 0644 or stricter accepted
- 1.7.2 banner quoting fixed (addresses https://github.com/ansible-lockdown/UBUNTU24-CIS-Audit/issues/30) - Thank you @LukeGotWood
- 1.7.2 and 1.7.3 check the dconf profile and dconf db settings
- 2.4.1.3 to 2.4.1.7 orphaned cron tests fixed
- 3.1.1 misindented file key and CIS_ID fixed
- 4.3.3 iptables flushed test reads rules, not policy headers
- 4.4.2.4 title and CIS_ID corrected
- 5.1.2 private key mode 0600 required when group is root
- 5.1.3 public host key perms test fixed: variable name, mask /133
- 5.1.2 and 5.1.3 find -name globs quoted
- 5.1.5 sshd_config.d Banner grep missing space fixed
- 5.3.3.4.1 and 5.3.3.4.2 brace expansion replaced with explicit file list
- 5.4.1.1 to 5.4.1.3 per-user checks flag each failing account
- 5.4.1.2 per-user check title, CIS_ID and level corrected
- 5.4.1.5 per-user INACTIVE check flags each failing account
- 5.4.1.6 exit status no longer depends on the last account
- 5.4.2.1 detects any non-root UID 0 account
- 5.4.2.2 and 5.4.2.3 GID 0 tests flag any non-root entry
- 5.4.2.5 root PATH test detects empty and relative entries
- 6.1.1.3, 6.1.2.2 to 6.1.2.4 and 6.1.3.3 journald tests read systemd-analyze cat-config
- 6.1.2.1.4 checks not enabled and not active instead of masked
- 6.1.3.5 rsyslog rule regexes anchored and escaped
- 6.1.3.6 remote log server variable, gate and YAML fixed
- 6.2.3.6 checks privileged rules, live rule test added
- 6.2.4.3 log_group setting and file group tests fixed
- 6.2.4.x config and tool tests report every non-compliant file
- 6.2.4.7 checks group owner instead of owner
- 6.3.2 cron check requires an aide --check or --update job
- 6.3.2 timer check no longer requires dailyaidecheck.service running
- 7.1.11 find exit status 123 accepted, find errors reported
- 7.1.13 lists SUID/SGID files, fails on unpackaged or modified ones
- 7.2.5 to 7.2.8 duplicate checks sort before uniq -d
- 7.2.9 owner check brace expansion and home field corrected
- 7.2.9 home directory mode check covers every home directory
- meta levels and level gates aligned to Profile Applicability
- titles aligned to the benchmark
- 3.3.5 and 3.3.8 IPv6 sysctl conf patterns allow the grep file prefix
- 3.3.11 sysctl grep pattern escape corrected
- 3.3.9 IPv6 router advert duplicate of 3.3.11 removed
- 4.1.1 counts a firewall only when its service is enabled and active
- 1.1.1.6 accepts the overlay module name
- 2.1.21 and 5.3.3.3.3 title separators fixed
- 6.2.3.20 grep reads -e 2 as a pattern, not an option
- 5.4.1.1, 5.4.1.2, 5.4.1.3 and 5.4.1.5 per-user checks skipped unless ubtu24cis_disruption_high

## Based on CIS v1.0.0 - July 26

- #26 thanks to @smd75jr level adjustments
- #27 thanks to @CyberiumShadow typo fixes
- run-audit script update
- goss download location and references updated
- contributing.md added
- removed V8 references
- Added missing test 4.1.1
- aligned variable naming wih remediation vars
- updated sshd_access logic to make it cleaner
- added missing 1.1.1.10
- Added 5.4.2.8
- updated missing vars for rsyslog
- fixed titles and numbering

## Based on CIS v1.0.0 - Branch [2026_April_QA]

### QA Validation

- Cross-repo validation performed against Private-UBUNTU24-CIS remediation role
- Molecule testing confirmed audit integration runs successfully
- **vars/CIS.yml:** Fixed `benchmark_version` from '2.0.0' to '1.0.0'
- **run_audit.sh:** Fixed `BENCHMARK_VER` from 2.2.0 to 1.0.0 and `BENCHMARK_OS`
- **LICENSE:** Updated copyright from '2024 MindPoint Group' to '2026 MindPoint Group - A Tyto Athene Company / Ansible Lockdown'
- **302 audit test titles:** Updated to match CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0 titles exactly

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
