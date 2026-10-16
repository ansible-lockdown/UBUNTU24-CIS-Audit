# Changes to Ubuntu24-CIS-Audit

## CIS Benchmark 2.0.0

## October 2026 - QA fixes

- CIS Benchmark 1.0.0 October 2026 QA fixes ported to 2.0.0 control IDs
- 1.1.1.9 and 1.1.1.10 accept hyphen and underscore module names
- 1.2.1.1 checks apt sources for Signed-By
- 1.2.1.2 checks apt weak dependencies are disabled
- 1.2.1.3, 1.2.1.6 and 1.2.1.9 permission checks fixed
- 1.3.1.1 checks apparmor-utils
- 1.3.1.3 requires profiles loaded and none in complain mode or unconfined
- 1.5.x sysctl checks catch a wrong value in any sysctl file
- 1.5.4 checks fs.suid_dumpable only
- 1.5.7 uses the benchmark apport check
- 1.6.1 checks pam_motd lines in sshd, login, su and gdm-password
- 1.6.4 uses the benchmark pam_motd script
- 1.6.9 checks only motd files that exist
- 1.6.10 uses ubtu24cis_sshd_banner_file
- 1.7.x dconf paths use ubtu24cis_dconf_db_name, header regexes escaped, lock files checked
- 2.1.2 gate corrected, mail ports and postfix inet_interfaces checked
- 2.1.3, 2.1.8 package names and 2.1.7, 2.1.13 service names corrected
- 2.1.5 checks kea packages and services
- 2.4.1.9 and 2.4.2.1 group and mode checks match the benchmark
- 4.1.2 checks ufw is active
- 4.1.3 to 4.1.5 accept the benchmark default policies
- 5.1.1 checks sshd_config.d file permissions
- 5.1.7, 5.1.16 and 5.1.18 value ranges corrected
- 5.1.23 checks post-quantum KexAlgorithms by OpenSSH version
- 5.2.2 checks !use_pty is absent
- 5.2.6 accepts 0 to 15 minutes
- 5.3.1.x version checks replaced with the benchmark upgradable check
- 5.3.3.1.x and 5.3.3.2.x value ranges corrected
- 5.4.2.6 checks /root/.profile and /root/.bashrc
- 5.4.2.7 uses the benchmark system account script
- 5.4.2.7 and 5.4.2.8 skipped unless ubtu24cis_disruption_high
- 6.1.1.1.x journald tests read systemd-analyze cat-config
- 6.1.1.1.4 uses the benchmark tmpfiles check
- 6.1.2.x run only when ubtu24cis_syslog_service is rsyslog
- 6.1.2.5 and 6.1.2.9 run only when a remote log server is set
- 6.1.2.3, 6.1.2.4, 6.1.2.6 and 6.1.2.7 checks fixed
- 6.1.3.1 checks every log file against the benchmark masks
- 6.2.1.4 and 6.2.2.x value checks fixed
- 6.2.3.x live rules checked with auditctl
- 6.2.3.22 accepts renameat2
- 6.2.4.x file permission, owner and group checks fixed
- 6.3.2 checks dailyaidecheck.timer only
- 7.1.2 checks /etc/passwd-
- 7.2.1, 7.2.2 and 7.2.4 checks fixed
- vars/CIS.yml: aide_scan timer, screensaver delays added

## Based on CIS v2.0.0 - August 2026

- Upgraded to CIS Ubuntu Linux 24.04 LTS Benchmark v2.0.0: 333 controls, 71 goss files added, 50 removed, 80 renumbered
- `vars/CIS.yml` benchmark_version and `run_audit.sh` BENCHMARK_VER set to 2.0.0
- New goss directories `section_3/cis_3.3.1` (IPv4) and `section_3/cis_3.3.2` (IPv6) replace `section_3/cis_3.3` and its `ipv6` subdirectory
- `section_4` reduced to `cis_4.1` (UFW); the nftables and iptables directories are removed along with the `ubtu24cis_firewall_package` branching in goss.yml
- `section_6` regrouped as `cis_6.1.1.1` (journald), `cis_6.1.2` (rsyslog) and `cis_6.1.3` (logfiles); the per-file `ubtu24cis_syslog_service` gates now live in the control files rather than the goss.yml globs
- Titles resynced from the v2.0.0 benchmark JSON

### Fixed

- `section_1/cis_1.1/cis_1.1.2.6.4.yml` and `cis_1.1.2.7.3.yml` gated on their sibling's toggle (`_1_1_2_6_1`, `_1_1_2_7_1`), so disabling that sibling silently dropped the noexec checks for /var/log and /var/tmp
- `section_2/cis_2.4/cis_2.4.1.3_7.yml` emitted the `file:` resource key inside the 2.4.1.3 gate only, so disabling 2.4.1.3 left the other four checks as orphaned keys; split into one file per control, which also brings them under the title check that the combined filename bypassed
- `section_3/cis_3.1/cis_3.1.1.yml` recorded `CIS_ID: 3.3.1` and indented its `file:` key by one space
- `section_5/cis_5.4.1/cis_5.4.1.2.yml` labelled its user_check test `CIS_ID: 5.4.1.1` with that control's profile
- 29 `meta.server`/`meta.workstation` values and 12 Jinja level gates realigned to the v2.0.0 Profile Applicability
- `section_2/cis_2.1` web server files renamed from `cis_2.1.18_*` to `cis_2.1.6_*` to match the control they now hold
- `section_1/cis_1.6/cis_1.6.6.yml` used `exec:` as a top-level resource, which goss does not recognise, so /etc/motd access was never actually checked; rewritten as a `file:` resource
- `section_6/cis_6.1.2/cis_6.1.2.5.yml` referenced `ubtu24cis_remote_log_host`, a variable this role does not define (it is `ubtu24cis_remote_log_server`)

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
