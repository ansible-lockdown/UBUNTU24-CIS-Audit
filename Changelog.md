# Changes to Ubuntu24-CIS-Audit

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
