# Intune Setup

This section describes the essential setup information that links Intune to the various Apple Services needed to achieve Automated Device enrollment and ongoing device management

## APNS Certificate

*Apple Push Notification Services are critical to the operation of MDM. For any action the MDM needs to take such as issuing a command or installing a profile the initial communication with the device is via APNS.*

To access the Intune UI, in a browser open [https://intune.microsoft.com/](https://endpoint.microsoft.com/) and log in with a **Entra ID** user ID that has the role of *Global Administrator* or *Intune Service Administrator* for your tenancy

Navigate to **Devices -> macOS -> macOS Enrollment**

Click **Apple MDM Push Certificate**

Check the box granting permission to send information to Apple

Click on **Download your CSR**

In a new browser window or tab open [https://identity.apple.com/pushcert/](https://identity.apple.com/pushcert/) and log in with a managed Apple ID.

*Do not use a personal Apple ID for this process as management the APNS certificate will be critical over the life of your device management solution and access via a personal Apple ID may become unavailable as staff change over time. Using a Managed Apple ID keeps control within the Apple Business Manager (or Apple School Manager) instance.*



Click **Create a Certificate**

Upload the CSR, create and download the certificate

You can log out and close this window/tab



Return to the **Intune UI**

Under **Apple ID** Enter the Managed Apple ID you used to log in and create the certificate

Under **Apple MDM push certificate** Select the certificate you just downloaded then click **Upload**

The Microsoft Documentation for this procedure is at [https://learn.microsoft.com/en-us/mem/intune/enrollment/apple-mdm-push-certificate-get](https://learn.microsoft.com/en-us/mem/intune/enrollment/apple-mdm-push-certificate-get)

## Automated Device Enrollment Token

*The Device Enrollment token enables secure communication between Apple Business Manager or Apple School Manager and the MDM to allow for Automated Device Enrollment.*

In the **Intune UI**

Navigate to **Devices -> iOS/iPadOS -> iOS/iPadOS Enrollment**

(Devices -> macOS -> macOS Enrollment will also work)

Click **Enrollment program tokens**

Click on **+ Add** to add a new token

Check the box granting permission to send information to Apple

Click on **Download your public key**



To access Apple Business Manager open a new browser window or tab and navigate to [https://business.apple.com](https://business.apple.com) and log in with a Managed Apple ID that has the role of Administrator or Device Enrolment Manager

Click your name at the bottom of the sidebar, and click **Preferences**

Under **Your MDM Servers** click the plus sign to **+ Add**

Name your MDM server and upload the **Public Key**

Download the Server Token by clicking on **Download Token** then clicking **Download Server Token**



In the **Intune UI**

Under **Apple ID** enter the Managed Apple ID you used to log in and  
create the Server Token

Under **Apple token** select the Server Token just downloaded then click **Next** then click **Create**

The Microsoft Documentation for this procedure is at  
[https://learn.microsoft.com/en-us/mem/intune/enrollment/device-enrollment-program-enroll-ios](https://learn.microsoft.com/en-us/mem/intune/enrollment/device-enrollment-program-enroll-ios)

## Apps and Books Token

*The Apps and Books Token (previously known as the Volume Purchase Program or VPP token) enables secure communication between Apple Business Manager or Apple School Manager and the MDM for the management of Apps and Book licensing*

In **Apple Business Manager**

In the sidebar click **Locations**

Click the plus sign to **+ Add**

Enter the details and create the new location

Click your name at the bottom of the sidebar, and click **Preferences**

Click **Payments and Billing**

Find the location you just created under **Server Tokens** and download the VPP token by clicking **Download**



In the **Intune UI**

Navigate to **Tenant administration -> Connectors and tokens -> Apple VPP Tokens**

Click **+ Create** to Create VPP Token

Under **Token Name** give the Token the same name used in ABM

Enter the Managed Apple ID used to create the VPP token in ABM

Upload the token file and click **Next**

<img src="assets/DYQ8Ta8mgLkWG.png" alt="" width="800" data-align="left"/>


Click through to complete the process.

You can ignore the Scope Tags page for this exercise

The Microsoft Documentation for this procedure is at  
[https://learn.microsoft.com/en-us/mem/intune/apps/vpp-apps-ios](https://learn.microsoft.com/en-us/mem/intune/apps/vpp-apps-ios#upload-an-apple-vpp-or-apple-business-manager-location-token)

***
<div style="page-break-after: always"></div>
