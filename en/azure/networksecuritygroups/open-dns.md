[![CloudSploit](https://cloudsploit.com/img/logo-new-big-text-100.png "CloudSploit")](https://cloudsploit.com)

# AZURE / Network Security Groups / Open DNS

## Quick Info

| | |
|-|-|
| **Plugin Title** | Open DNS |
| **Cloud** | AZURE |
| **Category** | Network Security Groups |
| **Description** | Determine if TCP or UDP port 53 for DNS is open to the public |
| **More Info** | While some ports such as HTTP and HTTPS are required to be open to the public to function properly, more sensitive services such as DNS should be restricted to known IP addresses. |
| **AZURE Link** | https://docs.microsoft.com/en-us/azure/virtual-network/manage-network-security-group |
| **Recommended Action** | Restrict TCP and UDP port 53 to known IP addresses |

## Detailed Remediation Steps
1. Log in to the Microsoft Azure Management Console.
2. Click on the search bar at the top and search for Network security groups. </br> <img src="/resources/azure/networksecuritygroups/open-dns/step2.png"/>
3. Select the "Network security group" that needs to be verified. </br> <img src="/resources/azure/networksecuritygroups/open-dns/step3.png"/>
4. Click on the "Name" of the selected "Network security group" to access the port configurations. </br> <img src="/resources/azure/networksecuritygroups/open-dns/step4.png"/>
5. In the "Overview" tab scroll down the page and check the "Inbound security rules" under the "Settings". </br> <img src="/resources/azure/networksecuritygroups/open-dns/step5.png"/>
6. If the "DNS" for port 53 with the protocol "TCP/UDP" is showing as "Allow" in column "Action" for all "Source" and "Destination" then the selected  "Network security group" has TCP/UDP port 53 for DNS open to the public. </br> <img src="/resources/azure/networksecuritygroups/open-dns/step6.png"/>
7. Repeat step number 2 - 6 to verify other "Network security groups." </br>
8. Navigate to the "Network security groups" and select the security group that needs to be modified for restricting the "TCP/UDP" port for DNS on port 53 to specific IP Address.</br><img src="/resources/azure/networksecuritygroups/open-dns/step8.png"/>
9. Scroll down the left navigation panel and choose "Inbound security rules" under "Settings."</br> <img src="/resources/azure/networksecuritygroups/open-dns/step9.png"/>
10. Click on the "DNS" protocol in the "Name" column and in the right pane under "Source" select the "IP Addresses" from the dropdown menu and enter the "Source IP addresses/CIDR ranges" as per the requirement, select the required Protocol and Action and click on the "Save" option at the top of the pane. </br> <img src="/resources/azure/networksecuritygroups/open-dns/step10.png"/>
11. Repeat step number 8 - 10 to restrict TCP and UDP port 53 to known IP addresses.</br>
