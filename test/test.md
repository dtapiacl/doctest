# Reset Keycloak 2FA

## 1. Summary  

**Issue Description**:  
A user is locked out of their Keycloak Profile when attempting to sign in and is stuck when prompted for their One Time Password (OTP). There is no Keycloak OTP on their MFA application.

**Root Cause**:
When a user gets a new phone, resets their current phone, or deletes their MFA app it may require us to reset their 2FA on Keycloak. The user usually fails to transfer over the MFA app to their new phone or before they reset their phone, causing them to be locked out of their Keycloak Account. It is also seen when a user uses an older device for MFA, an OS update on their older device will invalidate their MFA.

**Scope**:  
This applies to all users who use/need applications behind Keycloak.

**Note**:
This can apply to [keycloak.ls.lsst.org](keycloak.ls.lsst.org), whichever the user needs the MFA reset from. Just make sure to use the correct  URL.

## 2. Prerequisites

**Required Tools/Services**:  
- Network access to the Keycloak Server (Check your network access here: [keycloak.cp.lsst.org](keycloak.cp.lsst.org))
- The username of the affected user. This should be the same as the IPA username of the user.

**Credentials/Access**:  
- A valid login with a working OTP to the Keycloak Server. If you don't have that, there is an admin profile in the cp vault in 1Password.

## 3. Step-by-Step Procedures

### Step 1: Login to the Keycloak Server

**Login**:
Navigate to [keycloak.cp.lsst.org](keycloak.cp.lsst.org) and login.

![Login Screen of Keycloak](image1.png)

**Expected Outcome**:
You should be greated with the welcome page of Keycloak

![Welcome Screen of Keycloak](image2.png)

### Step 2: Get to the Users page of the Admin Panel

**Action**:  

First, click on Administration Console. Then click Users on the hamburger menu.

**Expected Outcome**:  

You should see the User's screen.

![Users Screen of Keycloak Admin Panel](image3.png)

### Step 3: Search for your user, click the user, and navigate to Credentials page

**Action**:  

Now, find your user by searching their username and click it to enter the User details screen. Now navigate to Credentials on the User menu.

**Expected Outcome**:

You should see the types of passwords associated with the user.

![User's credentials screen](image4.png)

### Step 4: Delete the OTP

**Action**:  

First, click the three dots on the row of the credential with the type of Otp. Then, select delete to remove the Otp for this user.

![Delete button](image5.png)

**Expected Outcome**:

A message should appear saying the credential was successfully deleted.

### Step 5: Have the user create a new MFA

**Action**:  

Have the user navigate to Keycloak and sign in to Keycloak using their IPA Credentials, then follow the instructions to create a new MFA.

![MFA Setup](image6.png)

**Expected Outcome**:

The user should now be able to sign in to Keycloak!

## 5. Troubleshooting  

### Common Issues

**Issues**:
* The user cannot get past the login screen of Keycloak.
* The Keycloak's page is not loading.
* The user still cannot access the desired services behind Keycloak.

**Solutions**:  
* Reset the user's IPA password.
* Ensure the VPN is on and connected. Also try to recconect the VPN.
* Ensure the user's IPA account has the correct groups assigned to them at [ipa1.cp.lsst.org](ipa1.cp.lsst.org).

## 6. Monitoring and Verification

**Monitoring**:  
Check the user's credentials details have the new OTP on the Admin Dashboard found on Step 3

**Verification Checks**:  
Make sure the OTP is working by having the user logout and log back in using the new OTP code.

## 8. History/Change Log

**Date**:  
2025-01-27 - User - Updated to include Docker image versioning.
