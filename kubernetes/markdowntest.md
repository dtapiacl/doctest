# Runbook name
## 1. Summary  
**Issue Description**:  
_Describe the problem (e.g., "The X service stops responding")_
**Root Cause**:
_Describe the root cause (e.g., "The pvc is full")_
**Scope**:  
_Specify the infrastructure components covered (e.g., "Applies to all web servers deployed in production under AWS EC2 using Docker.")_
## 2. Prerequisites
**Required Tools/Services**:  
_List any required tools, services, or configurations (e.g., "AWS CLI, Docker, GitHub access")_
**Credentials/Access**:  
_Outline required credentials (e.g., "Access to AWS EC2 instances with 'Admin' privileges.")_
## 3. Step-by-Step Procedures
### Step n: Step Name
**Action**:
_Description of the action_
```bash
command
```
**Expected Outcome**:
_Description of the output_
```bash
output
```
Example:
### Step 1: Initial Setup
**Action**:  
SSH into the target server using the following command:
```bash
ssh user@server-ip
```
**Expected Outcome**:  
You should see the server's command prompt.
```bash
[server-ip] $
```
## 5. Troubleshooting  
### Common Issues
1. **Issue**:
   - Description (e.g., "Cannot SSH into server.")  
   - **Solution**:  
     _(e.g., "Ensure the correct IP address and credentials are used. Verify that the security group allows SSH access.")_
## 6. Monitoring and Verification
**Monitoring**:  
_Specify any monitoring services/tools used (e.g., "Use Prometheus to monitor server health, or AWS CloudWatch for EC2 metrics.")_
**Verification Checks**:  
_List simple checks or queries to verify successful deployment (e.g., "Use `curl http://server-ip` to verify the server responds with the correct webpage.")_
## 8. History/Change Log
**Date**:  
_Description of the change (e.g., "2024-09-30 - User - Updated to include Docker image versioning.")_
