# Firewall Implementation and Configuration 

## Overview

In this setup, a FortiGate firewall within a VMware virtual environment is configured. The FortiGate firewall will be configured based on a provided network topology, ensuring proper access control and network segmentation. This setup aims to provide a secure and well-structured network environment. This documentation provides a step-by-step guide for configuring a FortiGate firewall based on the provided network topology. Follow the steps below to complete the configuration.

## Requirements

- VMware
- FortiGate Virtual Appliance
- Router and Switch FortiGate Virtual Appliance
- Setup Environment

## Network Topology

![network_topology](https://github.com/iamabdullahifti/firewall-config/assets/129957445/1a7a0a80-620f-405f-8155-55f1f587a075)


## Steps for Configuration

### Step 1: Access Firewall Console

Connect to the FortiGate firewall console.
Set the admin username and password.

![1](https://github.com/iamabdullahifti/firewall-config/assets/129957445/04d0634f-a134-43f3-835c-06395f00935c)


### Step 2: Login with the Admin Credentials Configured Earlier

Use the admin credentials set in the previous step to log in to the FortiGate GUI.

![2](https://github.com/iamabdullahifti/firewall-config/assets/129957445/9e630e4b-b9cd-425b-8f9d-289c71fa7081)


### Step 3: Change the Hostname

Navigate to the System settings.
Change the hostname of the FortiGate device as required.

![3](https://github.com/iamabdullahifti/firewall-config/assets/129957445/894468a0-6cfd-4a60-bb4e-eede1da76328)


### Step 4: View the Dashboard

Upon successful login, the dashboard of the FortiGate GUI will be displayed.

![4](https://github.com/iamabdullahifti/firewall-config/assets/129957445/d112a192-76a8-4a56-a71a-e365c2cf2ead)


### Step 5: Configure Super Admin User

Create a new user with the username "abdullah" and assign super admin privileges.
Delete the default admin account.

![5](https://github.com/iamabdullahifti/firewall-config/assets/129957445/f1150a4f-44fc-489a-a265-72f2f5518e00)


### Step 6: Configure Read-Only Admin Role

Create a new admin role with read-only permissions.

![6](https://github.com/iamabdullahifti/firewall-config/assets/129957445/982c91b3-aefa-481e-be93-d93ad3b94c9b)


### Step 7: Assign Read-Only Access to User "noor"

Create a new user with the username "noor".
Assign the read-only admin role to "noor".

![7](https://github.com/iamabdullahifti/firewall-config/assets/129957445/11e12917-845d-427e-8bdb-2720a1f0201a)


### Step 8: Customize prof_admin Role

Customize the "prof_admin" role to have read-only access to the network portion.
Create a new user with the username "rafay".
Assign the "prof_admin" role to "rafay".

![8](https://github.com/iamabdullahifti/firewall-config/assets/129957445/f3d72bcf-4307-4695-a24d-bf03ff006d80)


### Step 9: Confirm User Accounts Configuration

Ensure all user accounts ("abdullah", "noor", and "rafay") are configured correctly.

![9](https://github.com/iamabdullahifti/firewall-config/assets/129957445/59eea3b3-bc47-460a-b456-83e30daaa03e)


### Step 10: Verify Read-Only Access for "noor"

Log in with the "noor" account.
Verify that the account has read-only access.

![10](https://github.com/iamabdullahifti/firewall-config/assets/129957445/198d19a9-6c58-402c-8fc0-fd59127eea99)


### Step 11: Verify Customized Access for "rafay"

Log in with the "rafay" account.
Verify that the network options are not accessible.

![11](https://github.com/iamabdullahifti/firewall-config/assets/129957445/6794ddf9-a203-4e52-9955-e34ce229ac2a)

### Step 12: Verify Interface Status

Check that port 1 and port 2 are up on the firewall.

![12](https://github.com/iamabdullahifti/firewall-config/assets/129957445/38cdd1cf-ac87-456e-b265-8880c4687f42)


### Step 13: Configure WAN on Port 1

Assign IP address 192.168.247.200/24 to port 1.
Allow HTTP, PING, SSH, and FMG access on port 1.

![14](https://github.com/iamabdullahifti/firewall-config/assets/129957445/c4f03b97-1060-4938-83e6-2f4d9cc6dc28)


### Step 14: Configure LAN on Port 2

Assign IP address 10.1.1.1/24 to port 2.
Set the role to LAN and allow only ping access.

![15](https://github.com/iamabdullahifti/firewall-config/assets/129957445/a2979518-d1bc-492c-864c-d0a3e61ec961)


### Step 15: Configure DMZ on Port 3

Assign IP address 172.16.10.1/24 to port 3.
Set the role to DMZ and allow only ping access.

![16](https://github.com/iamabdullahifti/firewall-config/assets/129957445/8c2321d1-c53f-4530-b1ee-917016276fe7)


### Step 16: Confirm Interface Configuration

Verify that all interfaces are configured correctly.

![17](https://github.com/iamabdullahifti/firewall-config/assets/129957445/4bef18c7-d13f-490c-aa95-3d5a4548c9fb)


### Step 17: Create LAN-Internet Access Policy

Navigate to Policy & Objects.
Create a new policy for LAN-Internet access.
Place this policy above the implicit deny rule.

![18](https://github.com/iamabdullahifti/firewall-config/assets/129957445/12c1ce95-8644-4239-835a-e734729563b4)


### Step 18: Create LAN-DMZ Access Policy

Navigate to Policy & Objects.
Create a new policy for LAN-DMZ access.
Place this policy above the previous LAN-Internet access policy.

![19](https://github.com/iamabdullahifti/firewall-config/assets/129957445/f05b3982-4433-4296-a57c-2daa2cf0b370)


### Step 19: View the Policy Configuration

![20](https://github.com/iamabdullahifti/firewall-config/assets/129957445/e916a308-a3e8-4258-bea7-b2a11fd1c1a9)


# Conclusion

Following these steps ensures that the FortiGate firewall is configured correctly according to the specified requirements and network topology. This documentation serves as a guide for administrators to replicate the configuration process. For any issues or further customization, refer to the FortiGate documentation or contact technical support.

## Contributions

Contributions are welcome! Please submit pull requests for any improvements or changes.

## License

This project is licensed under the MIT License.
