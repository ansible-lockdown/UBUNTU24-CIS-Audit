# Changes to Ubuntu24-CIS-Audit

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
