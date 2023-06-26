# Ansible Role: Ubuntu STIG

This [Ansible](https://www.ansible.com) role will apply the current [DISA Security Technical Implementation Guide (STIG)](https://public.cyber.mil/stigs) 
configuration to an Ubuntu system.  This role is neither sponsored by nor maintained by the Department of Defense or the Defense Inforamtion System Agency.
This is a personal project of mine to have a role that is easier to apply and maintain than the official [DISA release](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_CAN_Ubuntu_20-04_LTS_V1R8_STIG_Ansible.zip).

**WARNING: DO NOT BLINDLY ACCEPT ALL STIG CONFIGURATIONS WHEN SECURING YOUR SERVER.**  Take the time to review each setting for applicability in your use case.

## Version Information

* Version: 1.8.0
* Baseline Ansible Role: [V1 R8 STIG Ansible Role](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_CAN_Ubuntu_20-04_LTS_V1R8_STIG_Ansible.zip)
* STIG Release: [V1 R8 STIG](https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_CAN_Ubuntu_20-04_LTS_V1R8_STIG.zip)

## Requirements

Ubuntu 20.04 (Focal Fossa) or 22.04 (Jammy Jellyfish) are required for this role for now.  I intend to extend this role to add the
Ubuntu 18.04 (Bionic Beaver) STIG configuration in a future release.

## Role Variables

There are a significant number of role variables associated with this implementation.  The official release maintains two variables for each configuration setting:

* ubuntu2004STIG_stigrule_VULNID_Manage: A Boolean value specifying whether this settings should be configured or skipped (True = managed)
* ubuntu2004STIG_stigrule_VULNID__SETTINGNAME_Value: The configuration value to set

These values are set in the [defaults/main.yml] file and should be reviewed for any deviations required for your business application.

DISA provides an easy to use [STIG Viewer](https://public.cyber.mil/stigs/srg-stig-tools/) application to review the various settings.  Download this tool and
the associated STIG referenced above.

## Dependencies

There are no other dependencies for this role.  However, I will maintain an additional ansible role to apply additional STIG settings that are not covered by the official Ansible release.

## Example Playbook


Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: ubuntu_stig


## License

MIT

## Author Information

Alex Ackerman, Twitter @Darkhonor
