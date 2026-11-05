# Changes to Ubuntu24-CIS-Audit

## CIS Benchmark 1.0.0

## November 2026 - QA fixes

- run_audit.sh OS name and version default when /etc/os-release is missing
- 1.1.2.1.2 to 1.1.2.1.4 check tmp.mount when /tmp is a systemd unit
- 1.3.1.1 apparmor-utils checked
- 1.3.1.2 every grub linux line checked
- 1.4.1 checks grub.cfg
- 1.5.3 non-existent coredump service test removed
- 1.5.5 accepts apport not installed
- 1.6.5 and 1.6.6 accept 644 or stricter
- 1.7.4 to 1.7.10 dconf paths, patterns and lock file names fixed
- 2.1.2 avahi-daemon package name
- 2.1.4 named.service mask path
- 2.1.6 vsftpd package name
- 2.1.10 ypserv.service mask path
- 2.1.16 tftp.socket test removed
- 2.1.21 gate inverted, postconf and listening port checks
- 2.2.1 gated on ubtu24cis_nis_client_required
- 2.3.1.1 ntp and timesyncd checked with chrony
- 2.4.1.8 and 2.4.2.1 accept crontab or daemon group
- 3.1.2 wireless module check per module
- 3.3.2 and 3.3.8 skipped on routers, send_redirects spacing
- 4.2.3 ufw status active checked
- 4.2.6, 4.4.2.x and 4.4.3.x automated checks replace Manual stubs
- 4.2.7 accepts deny, reject or disabled
- 5.1.1 sshd_config.d files checked, 0600 or stricter
- 5.1.4 checks sshd -T for allow/deny directives
- 5.1.6, 5.1.12 and 5.1.15 fail when sshd -T fails
- 5.1.17 MaxSessions range anchored
- 5.2.2 !use_pty checked
- 5.2.6 timestamp_timeout range
- 5.3.1.1 to 5.3.1.3 version pins removed, minimum version checked
- 5.3.3.1.x deny, unlock_time and root_unlock_time ranges
- 5.3.3.2.x and 5.3.3.3.1 ranges, dictcheck and enforcing only forbid 0
- 5.4.1.3 PASS_WARN_AGE range
- 5.4.2.5 root PATH checks
- 5.4.2.6 checks /root/.bashrc
- 5.4.2.7 and 5.4.2.8 shell logic, visible skip without disruption_high
- 5.4.3.3 umask regexps
- 6.1.1.4 journald stopped test removed
- 6.1.3.4 FileCreateMode 0640 or stricter
- 6.1.3.8 logrotate frequency and rotate checked
- 6.1.4.1 log file masks and ownership
- 6.2.1.4 backlog limit 8192 or more
- 6.2.2.4 space_left_action anchored
- 6.2.3.3 uses the sudo log variable
- 6.2.3.4 clock_settime a0=0x0 rules
- 7.1.2 checks /etc/passwd-
- 7.1.10 opasswd may be absent, opasswd.old checked
- 7.2.1 and 7.2.2 shadowed password and empty field checks
- 7.2.4 shadow primary group checked
- 7.2.10 interactive user homes, .netrc 0600 allowed
- per-profile level gates on system_type for 1.1.1.9, 1.7.1, 1.7.6, 1.7.7, 2.1.1, 2.1.2, 2.1.11, 2.1.20, 3.1.2, 3.1.3, 5.1.8, 5.1.9
- 1.5.3 coredump.conf [Coredump] section, skipped when systemd-coredump not installed
- 1.7.2 and 1.7.3 check the gdm profile and gdm.d keyfiles
- 2.4.2.1 skipped when at not installed
- 5.1.5, 5.1.7-5.1.11, 5.1.13, 5.1.14, 5.1.16-5.1.22 read sshd -T
- 5.1.17 MaxSessions also checks sshd_config.d
- 5.2.1 checks the configured sudo package
- 6.3.2 tests dailyaidecheck.timer and service only
- vars: ubtu24cis_sudo_package, ubtu24cis_coredump_installed, ubtu24cis_at_installed, ubtu24cis_aide_scan timer, system_type

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
