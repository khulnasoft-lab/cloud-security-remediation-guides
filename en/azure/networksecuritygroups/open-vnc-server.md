[![CloudSploit](https://cloudsploit.com/img/logo-new-big-text-100.png "CloudSploit")](https://cloudsploit.com)

# AZURE / Network Security Groups / Open VNC Server

## Quick Info

| | |
|-|-|
| **Plugin Title** | Open VNC Server |
| **Cloud** | AZURE |
| **Category** | Network Security Groups |
| **Description** | Determine if TCP port 5900 for VNC Server is open to the public |
| **More Info** | While some ports such as HTTP and HTTPS are required to be open to the public to function properly, more sensitive services such as VNC Server should be restricted to known IP addresses. |
| **AZURE Link** | https://docs.microsoft.com/en-us/azure/virtual-network/manage-network-security-group |
| **Recommended Action** | Restrict TCP port 5900 to known IP addresses |

## Detailed Remediation Steps
1. Log in to the Microsoft Azure Management Console.
2. Click the search bar at the top and search for Network security groups. </br> <img src="/resources/azure/networksecuritygroups/open-vnc-server/step2.png"/>
3. Select the "Network security group" that needs to be verified. </br> <img src="/resources/azure/networksecuritygroups/open-vnc-server/step3.png"/>
4. Click on the "Name" of the selected "Network security group" to access the port configurations. </br> <img src="/resources/azure/networksecuritygroups/open-vnc-server/step4.png"/>
5. In the "Overview" tab scroll down the page and check the "Inbound security rules" under the "Settings". </br> <img src="/resources/azure/networksecuritygroups/open-vnc-server/step5.png"/>
6. If the "VNC-Server" for port 5900 with the protocol "TCP" is showing as "Allow" under column "Action" for all "Source" and "Destination" then the selected  "Network security group" has TCP port 5900 for "VNC-Server" open to the public. </br> <img src="/resources/azure/networksecuritygroups/open-vnc-server/step6.png"/>
7. Repeat step number 2 - 6 to verify other "Network security groups". </br>
8. Navigate to the "Network security group" and select the security group that needs to be modified for restricting the "TCP" port for "VNC-Server" on port 5900 to specific IP Address.</br> <img src="/resources/azure/networksecuritygroups/open-vnc-server/step8.png"/>
9. Scroll down the left navigation panel and choose "Inbound security rules" under "Settings."</br> <img src="/resources/azure/networksecuritygroups/open-vnc-server/step9.png"/>
10. Click on the "VNC-Server" protocol in the "Name" column and in the right pane under "Source" select the "IP Address" from the dropdown menu and enter the "Source IP addresses/CIDR ranges" as per the requirement, select the required "Protocol" and "Action" and click on the "Save" option at the top of the pane. </br> <img src="/resources/azure/networksecuritygroups/open-vnc-server/step10.png"/>
11. Repeat step number 8 - 10 to restrict TCP port 5900 for VNC-Server to known IP addresses.</br>
