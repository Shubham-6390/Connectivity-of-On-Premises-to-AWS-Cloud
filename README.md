# On-Premises to AWS Cloud Connectivity | Hybrid Cloud Networking

A hands-on hybrid cloud networking project demonstrating secure connectivity between an on-premises network in Mumbai and Amazon Web Services (AWS) in the Ohio region using AWS Site-to-Site VPN and a Fortinet FortiGate firewall.

The project integrates Windows Server 2022 Active Directory with AWS Directory Service and implements role-based access control (RBAC) for AWS resources.

## Project Overview

Organizations often maintain on-premises infrastructure while adopting cloud services. This project demonstrates how an on-premises environment can communicate securely with AWS resources through an IPsec Site-to-Site VPN connection.

The implementation covers:

* Hybrid network connectivity between on-premises infrastructure and AWS.
* AWS VPC and custom network configuration.
* FortiGate firewall configuration as the Customer Gateway.
* AWS Site-to-Site VPN with two tunnels.
* Windows Server 2022 deployment as an Active Directory Domain Controller.
* AWS Directory Service integration.
* IAM-based access control for EC2 and S3.
* Private IP connectivity verification.

## Architecture

![On-Premises to AWS Hybrid Cloud Architecture](images/hybrid-cloud-architecture.png)

> Replace the image path with your actual architecture diagram.

## Project Environment

| Component            | Configuration                            |
| -------------------- | ---------------------------------------- |
| On-Premises Location | Mumbai, India                            |
| AWS Region           | US East (Ohio)                           |
| Firewall             | Fortinet FortiGate                       |
| VPN Type             | AWS Site-to-Site VPN                     |
| VPN Tunnels          | Two                                      |
| Cloud Network        | Amazon VPC                               |
| Operating System     | Windows Server 2022                      |
| Directory Service    | Active Directory / AWS Directory Service |
| Access Management    | AWS IAM and RBAC                         |
| Connectivity Testing | ICMP / Private IP communication          |

## Technologies & Services Used

| Technology              | Purpose                                 |
| ----------------------- | --------------------------------------- |
| Amazon VPC              | Isolated cloud networking               |
| AWS Site-to-Site VPN    | Encrypted hybrid connectivity           |
| Customer Gateway        | Represents the on-premises VPN endpoint |
| Virtual Private Gateway | AWS VPN endpoint attached to the VPC    |
| Fortinet FortiGate      | On-premises firewall and VPN endpoint   |
| Windows Server 2022     | Active Directory Domain Controller      |
| AWS Directory Service   | Managed directory integration           |
| AWS IAM                 | Identity and permissions management     |
| Route Tables            | Traffic routing between networks        |
| Security Groups         | Instance-level network access control   |
| ICMP                    | Connectivity verification               |

## Network Architecture

### 1. On-Premises Environment

The on-premises environment represents an organizational network located in Mumbai.

Components include:

* Fortinet FortiGate firewall.
* Internal network resources.
* Windows Server 2022.
* Active Directory Domain Controller.
* Private network addressing.

### 2. AWS Cloud Environment

The AWS environment is deployed in the US East (Ohio) region.

Components include:

* Custom VPC.
* Subnet configuration.
* Route tables.
* Virtual Private Gateway.
* Customer Gateway configuration.
* Site-to-Site VPN connection.
* EC2-based cloud resources.

### 3. VPN Connectivity

The Site-to-Site VPN establishes encrypted IPsec connectivity between the FortiGate firewall and AWS.

Two VPN tunnels are configured to provide redundancy.

Routing is configured to allow communication between the on-premises network and AWS private network.

## Implementation Steps

### Step 1: AWS VPC Configuration

* Created a custom VPC with an appropriate CIDR block.
* Configured subnet and routing requirements.
* Prepared network resources for hybrid connectivity.

### Step 2: Customer Gateway Configuration

* Configured a Customer Gateway in AWS representing the FortiGate firewall.
* Specified the appropriate public endpoint and routing configuration.

### Step 3: Virtual Private Gateway

* Created a Virtual Private Gateway.
* Attached it to the custom VPC.
* Prepared the AWS endpoint for Site-to-Site VPN connectivity.

### Step 4: Site-to-Site VPN Configuration

* Created an AWS Site-to-Site VPN connection.
* Configured two VPN tunnels.
* Applied the relevant tunnel configuration to FortiGate.
* Verified tunnel status and routing.

### Step 5: FortiGate Firewall Configuration

* Configured IPsec VPN parameters.
* Configured network routes.
* Applied firewall policies for authorized traffic.
* Enabled forwarding functionality for the firewall EC2 instance where applicable by disabling Source/Destination Check.

### Step 6: Windows Server 2022 and Active Directory

* Deployed Windows Server 2022.
* Configured the server as an Active Directory Domain Controller.
* Created and managed domain users.
* Configured directory-related access requirements.

### Step 7: AWS Directory Service and Access Management

* Integrated directory services with the AWS environment.
* Configured separate access permissions for administrative users.
* Applied role-based access control.

Example access separation:

| User   | Access                    |
| ------ | ------------------------- |
| admin1 | EC2 administrative access |
| admin2 | S3 access                 |

Permissions were designed around the principle of least privilege.

## Connectivity Verification

The following checks were performed:

* VPN tunnel status verification.
* Route table validation.
* Firewall policy verification.
* Private IP connectivity testing.
* ICMP-based communication testing between network environments.

### Expected Connectivity Flow

```text
On-Premises Network (Mumbai)
          |
          v
Fortinet FortiGate Firewall
          |
          v
IPsec Site-to-Site VPN
      (Two Tunnels)
          |
          v
AWS Virtual Private Gateway
          |
          v
Amazon VPC (Ohio)
          |
          v
Private AWS Resources
```

## Key Learning Outcomes

Through this project, I gained practical exposure to:

* Hybrid cloud networking.
* Site-to-Site VPN architecture.
* IPsec tunnel configuration concepts.
* AWS VPC and routing.
* Firewall policies and traffic forwarding.
* Windows Server administration.
* Active Directory and directory integration.
* IAM permissions and RBAC.
* Network troubleshooting and connectivity validation.

## Challenges & Troubleshooting

| Area                     | Troubleshooting Approach                                    |
| ------------------------ | ----------------------------------------------------------- |
| VPN tunnel connectivity  | Verified tunnel configuration, status, and IPsec parameters |
| Private IP communication | Checked routing, firewall policies, and Security Groups     |
| Traffic forwarding       | Reviewed routing and Source/Destination Check configuration |
| Directory access         | Verified domain configuration and user permissions          |
| AWS access control       | Reviewed IAM policies and least-privilege permissions       |

## Future Enhancements

* Configure centralized logging and monitoring.
* Implement AWS CloudWatch alarms for VPN tunnel status.
* Automate VPC and VPN-related infrastructure using Terraform.
* Explore AWS Transit Gateway for multi-VPC connectivity.
* Implement additional network security controls.
* Document failover testing between VPN tunnels.

## Author

**Shubham Dharmendra Gupta**

B.E. Information Technology | AWS Certified Solutions Architect – Associate

* GitHub: [Shubham-6390](https://github.com/Shubham-6390)
* LinkedIn: [Shubham Gupta](https://linkedin.com/in/shubham-gupta-cloud)
* Portfolio: [Personal Portfolio](https://shubham-6390.github.io/Shubham-Portfolio)

---

**Project Category:** Hybrid Cloud | AWS Networking | Infrastructure | Windows Server | Network Security

*Developed as a hands-on cloud infrastructure project to understand secure communication between on-premises environments and AWS.*
