# IT Support & Service Desk Simulation Portfolio

## 📊 Laboratory Overview
This repository documents technical incidents, initial troubleshooting data, and precise resolution steps performed within an enterprise service desk simulator environment. The purpose of this laboratory is to track, triage, and process a high volume of Tier 1 user requests while enforcing corporate security policies and maintaining service availability.

### Operational Metrics
* **Environment**: Tier 1 Support Desk Simulation (Multi-Floor Corporate Office & Remote Users)
* **Core Competencies Verified**: Identity & Access Management (IAM), Hardware Triage, Access Layer Networking, Remote Administration, and User Provisioning.

---

## 🛠️ Processed Ticket Logs

### 1. Identity Verification & Password Management (Active Directory)
* **Ticket Reference**: INC449537 (High Priority)
* **User/Department**: Quinn Adams | Support (Floor 3)
* **Issue Description**: User forgot their password after returning from a two-week vacation. User has back-to-back meetings starting in 15 minutes and requires immediate email access.
* **User Troubleshooting Performed**: Forgot password during vacation. Stated manager approved the reset. Did not remember employee ID.
* **My Action & Resolution Steps**: 
  1. Opened Tools → Directory and searched for the user by the username provided in the ticket.
  2. Clicked the user account to select them.
  3. Clicked "Send Verification Code" to verify identity, enforcing security policy that manager approval alone is insufficient.
  4. Entered the verification code provided by the user.
  5. Cleared identity verification and clicked "Reset Password" to generate a secure temporary password.

### 2. Hardware Lifecycle & Remote Asset Deployment
* **Ticket Reference**: INC714649 (Critical Priority)
* **User/Department**: Patrick O'Brien | Support (Remote / WFH)
* **Issue Description**: Remote agent's corporate laptop is completely unresponsive on a work-from-home day, blocking them from accessing the softphone queue.
* **User Troubleshooting Performed**: Held the power button several times, tried two different chargers, and verified functionality on a known-good wall outlet. Observed no lights, no fan, and no blinking power LED.
* **My Action & Resolution Steps**:
  1. Diagnosed the system as a total power/hardware failure based on the lack of status lights, fans, or a breathing LED (confirming the device was dead, not asleep).
  2. Coordinated with the agent over Team Chat to disconnect all peripherals, execute a flea-power drain by holding the power button for 30 seconds, and press it once more; confirmed the device remained dark and a bad charger was successfully ruled out.
  3. Opened Tools → Computer Deployment and initiated Server Imaging to build a replacement laptop matching the specific customer support image profile found in corporate hardware documentation.
  4. Opened Tools → Asset Management → Add Asset, registered the unique serial number of the new laptop, and adjusted its status to "Ready."
  5. Processed the checkout sequence within Asset Management by locating the user's profile and selecting "Check out replacement."
  6. Opened Tools → Ship Manager and messaged the remote agent to collect and confirm their direct shipping address.
  7. Selected the staged hardware asset (Laptop) inside the shipping portal and checked the box to "Include return label."
  8. Configured the logistics delivery tier to "Rush Priority (Same day)" and executed the shipment.
  9. Logged instructions to have the agent pack the defective hardware and return it to corporate IT using the provided prepaid return label upon delivery.

### 3. Access Layer Network Triage & Device Power-Cycling
* **Ticket Reference**: INC0012858 (Critical Priority)
* **User/Department**: Mike Reeves | Facilities (Floor 3)
* **Issue Description**: Total internet and website connectivity failure affecting all users and conference rooms across the entire 3rd floor. Customer service team is blocked from accessing the CRM.
* **User Troubleshooting Performed**: Isolated the scope of the issue by checking connectivity with the 2nd-floor staff, confirming that 2nd-floor network connectivity was stable and functioning normally.
* **My Action & Resolution Steps**:
  1. Opened Tools → Server Room to access the physical/virtual network rack management interface.
  2. Navigated directly to the "Devices" tab within the server room utility.
  3. Located the specific network appliance labeled "Floor 3 Switch."
  4. Clicked the physical "Power" toggle button on the interface to initiate a full hardware reboot of the switch.
  5. Monitored the diagnostic console for 30–60 seconds while waiting for the network operating system to cycle and come back online.
  6. Initiated contact with the user over Team Chat to verify local connectivity; successfully resolved and closed the incident upon the user's confirmation that internet access was restored.

### 4. Remote Support, VPN Verification & Network Drive Mapping
* **Ticket Reference**: INC851727 (Medium Priority)
* **User/Department**: Diana Foster | HR (Floor 2)
* **Issue Description**: A recently transferred employee was missing the team's shared department folder on their computer. Attempting to input the direct file path generated a "network path not found" error.
* **User Troubleshooting Performed**: Verified with the department manager that access was authorized. Noted that the network drive was completely missing from the local PC.
* **My Action & Resolution Steps**:
  1. Opened Tools → Remote Support and initialized a remote desktop session by clicking "Connect" next to the user's PC.
  2. Accessed the user's desktop environment, opened the corporate "VPN Client" application, and clicked "Connect" to establish a secure tunnel required to authenticate with the on-premises file server.
  3. Opened Tools → Documentation, navigated to the "File Server" directory, and located the exact Universal Naming Convention (UNC) path dedicated to the Human Resources department.
  4. Returned to the user's active remote desktop session, launched File Explorer, navigated to "This PC," selected the context menu option (See more), and clicked "Map network drive."
  5. Pasted the verified HR department UNC path into the network folder field and executed the "Map Drive" protocol.
  6. Verified that the mapped network volume automatically initialized and opened on the user's desktop, confirming stable data read/write access.

### 5. Display Failure & Hard Power-Cycle Diagnostic Workflows
* **Ticket Reference**: INC343263 (Critical Priority)
* **User/Department**: Julia Chen | Marketing (Floor 2)
* **Issue Description**: User's laptop failed to boot up properly in the morning. The screen remained completely black while the power light continuously blinked.
* **User Troubleshooting Performed**: Pressed the power button a few times and verified the device was actively plugged into a power source. Observed the power light slowly blinking continuously while the screen remained black.
* **My Action & Resolution Steps**:
  1. Identified that the slowly blinking power LED indicated a system in a deep sleep state rather than a complete power failure, prioritizing wake-up and hardware drainage protocols.
  2. Coordinated with the user over Team Chat, instructing them to disconnect all external peripherals, including the docking station, charging block, external monitors, and USB accessories.
  3. Walked the user step-by-step through a complete hard reset procedure, instructing them to hold the physical power button down for a full 30 seconds until all residual status indicators and internal fans completely shut down, then press it once normally.
  4. Provided explicit, written technical steps via chat instead of using generic terminology to ensure user comprehension and successful execution.
  5. Confirmed that the hard power cycle successfully cleared the frozen sleep state, forced the laptop to execute a clean boot sequence, and restored full display functionality.

### 6. Role-Based Access Control (RBAC) & Privileged Group Management
* **Ticket Reference**: INC112071 (High Priority)
* **User/Department**: David Lee | Support (Floor 1)
* **Issue Description**: Newly promoted department head blocked from accessing budget reports, approving purchase requests, and using management tools due to retaining standard department permissions.
* **User Troubleshooting Performed**: Verified that current account permissions only granted standard access. Confirmed HR and departmental Vice President had formally authorized the management access.
* **My Action & Resolution Steps**:
  1. Opened Tools → Directory and executed a search query for the requester's user account.
  2. Opened the employee's active directory profile configuration screen.
  3. Located the group membership settings, entered "Management" in the "Add to group..." field, and executed the "Add" protocol.
  4. Inspected the updated account object to confirm that the privileged security group was successfully attached, granting immediate administrative and approval rights.

### 7. Directory Provisioning & Identity Onboarding Access
* **Ticket Reference**: INC0012853 (Medium Priority)
* **Submitted by**: Robert Torres | Engineering 
* **Issue Description**: Intake request from Human Resources to configure directory credentials and software group access for an incoming Junior Developer starting Monday at 9 AM.
* **User Troubleshooting Performed**: Stated that the user needs the environment ready for orientation. Provided standard user variables (Jennifer Torres, Username: `jtorres`).
* **My Action & Resolution Steps**:
  1. Opened Tools → Directory from the main management dashboard interface.
  2. Selected the configuration command to generate a "New user."
