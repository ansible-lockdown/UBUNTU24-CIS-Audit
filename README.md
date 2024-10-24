# Ubuntu 24.04 Goss config

## Overview

### Based on CIS Benchmark for Ubuntu 24.04 LTS Benchmark v1.0.0

[Centre For Internet Security]

This repository is set of configuration files and directories to run the audit of the relevant benchmark of Ubuntu 24.04 servers

This is configured in a directory structure level.

## variables

file: vars/{benchmark_type}.yml

Please refer to the file for all options and their meanings

The listed variable for every control/benchmark can be turned on/off or section

- Other controls
  - enable_selinux
  - run_heavy_tasks

- Bespoke options

  If a site has specific options e.g. password complexity these can also be set.

## Requirements

goss >= 0.4.4
root privileges

## Branches

If running as part of the ansible playbook, this will pull in the relevant branch for the version of benchmark you are remediating.

- e.g. v1.0.0 will pull in branch benchmark-v1.0.0

Devel is normally the latest benchmark version, so maybe different from the version of benchmark you wish to test.
Details will show in the README as part of the remedation as to the benchmark for the version it is written for.

## Usage

Fot the latest information on audit and how it can be used please visit

[Read the Docs - Audit]

## Extra settings

Ability to add your own requirements is available in several sections

## Support

[Discord Community Discussions]

[Enterprise Support]

[MindPoint Group]

## Links and Further information

- [Goss]
  - [Goss documentation]
- [Centre For Internet Security]

<!----
README Links
---->

[benchmark-type]: CIS
[OS-VERSION]: Ubuntu2404
[os-type]: Linux
[Centre For Internet Security]: https://www.cisecurity.org
[Read the Docs - Audit]: https://ansible-lockdown.readthedocs.io/en/latest/audit/getting-started-audit.html

[goss documentation]: (https://github.com/goss-org/goss/blob/master/README.md)

[Goss]: https://goss.rocks
[DISA STIG]: https://public.cyber.mil/stigs

[MindPoint Group]: https://mindpointgroup.com/cybersecurity-consulting/automate/baseline-modernization#GH_LockdownReadMe
[Discord Community Discussions]: https://www.lockdownenterprise.com/discord
[Enterprise Support]: https://lockdownenterprise.com#GH_LockdownReadMe
