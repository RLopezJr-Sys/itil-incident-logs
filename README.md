# itil-incident-logs
Hands-on Linux sysadmin infrastructure labs via KodeKloud, documented as professional ITIL-compliant incident reports.

# 2026-10-05-create-custom-apache-user.md
Documenting my journey from Tier 1 Support to SysAdmin/Cloud Admin through real-world Linux troubleshooting labs, automated configurations, and rigorous incident documentation.


# Incident Report / Operational Task: Create Custom Apache User

- **Date:** October 5, 2026
- **Datacenter:** Stratos Datacenter
- **Target Server:** Application Server 3 (`stapp03`)
- **Status:** Resolved / Completed

## Overview
As part of xFusionCorp Industries' security hardening initiative for web applications, unique and custom Apache users are required on individual application servers to enhance security boundaries. This task required provisioning a dedicated user account with specific UID and home directory mappings on Application Server 3.

## Specifications
- **Username:** `siva`
- **UID:** `1106`
- **Home Directory:** `/var/www/siva`

## Diagnostics & Execution Steps
1. **Access Control:** Logged into the central control jump-host (`thor@jump-host`)[cite: 2].
2. **Remote Connection:** Established an SSH session to Application Server 3 utilizing the designated administrative user account (`banner@stapp03`) and corresponding credentials.
3. **User Provisioning:** Executed the `useradd` utility with elevated privileges (`sudo`) to configure the user with the exact parameter constraints:
   ```bash
   sudo useradd -u 1106 -d /var/www/siva -m sivactures, and remote multi-node server management


**Verification:**
Post-execution validation was performed to confirm account creation, UID assignment, and directory structure integrity
id siva && ls -ld /var/www/siva

**Output:**
uid=1106(siva) gid=1106(siva) groups=1106(siva)
drwx------ 2 siva siva 4096 Oct  5 09:39 /var/www/siva

**Remediation / Result:**
The user account siva was successfully created with UID 1106 and initialized with the correct home directory permissions under /var/www/siva. Task verified and closed successfully on the KodeKloud evaluation platform.




# 2026-10-05-create-nautilus-admin-group.md
Practical Linux system administration labs and ITIL-compliant incident reports documenting multi-node infrastructure provisioning and troubleshooting.

# Incident Report: Multi-Node User Provisioning & Group Access Control

**Incident ID:** INC-2026-0412  
**Date:** October 5, 2026  
**Environment:** KodeKloud Engineer Labs (`stapp01`, `stapp02`, `stapp03`)  
**Status:** Resolved / Closed

## **Incident Overview** ##
Objective: Standardize user access and role assignments across a multi-node Linux application server environment in accordance with simulated enterprise security policies.

Source/Trigger: Internal infrastructure provisioning ticket via KodeKloud lab simulation.

Problem Statement: A new administrative user (sonya) and a dedicated security group (nautilus_admin_users) needed to be provisioned uniformly across all target app servers to ensure proper role-based access control (RBAC).
