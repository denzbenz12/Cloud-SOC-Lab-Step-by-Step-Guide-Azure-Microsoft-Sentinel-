# Cloud-SOC-Lab-Step-by-Step-Guide-Azure-Microsoft-Sentinel-


1. Create an Azure Account

Sign up for an Azure account (free tier is sufficient).

Confirm billing and access the Azure Portal. <br>



2. Create a Resource Group

In the Azure Portal, create a Resource Group.

Choose a region close to your location.

This will contain all lab resources.



3. Deploy a Virtual Machine

Create a Windows Virtual Machine.

Assign it to the resource group.

Enable public IP access.

Set a username and password for RDP access.



4. Expose the VM to the Internet (Intentionally)

Open the Network Security Group (NSG) attached to the VM.

Allow inbound traffic on:

RDP (Port 3389) from any source.

This makes the VM intentionally vulnerable to attract brute-force attempts.



5. Disable Windows Firewall (Lab Purpose Only)

RDP into the VM.

Disable Windows Defender Firewall.

This ensures logs capture more visible activity.

⚠️ This is for lab learning only, not production use.



6. Verify Security Event Logging

On the VM, open Event Viewer.

Confirm Security logs are being generated (especially failed login attempts).



7. Create a Log Analytics Workspace

In Azure, create a Log Analytics Workspace.

Associate it with the same resource group.

This workspace will store all security logs.



8. Enable Microsoft Sentinel

Open Microsoft Sentinel in Azure.

Attach it to the Log Analytics Workspace.

Sentinel now acts as the SIEM for the lab.



9. Connect the VM to Sentinel

In Sentinel, enable the Windows Security Events data connector.

Configure it to collect All Security Events.

Verify logs begin appearing in the workspace.



10. Generate Real Attack Data

Leave the VM exposed for several hours.

Allow real-world attackers to attempt RDP logins.

Failed login attempts will populate Sentinel logs.



11. Query Logs Using KQL

Open Logs in Microsoft Sentinel.

Run KQL queries to analyze:

Failed login attempts

Source IP addresses

Event IDs (e.g., 4625)

Confirm real attack data is visible.



12. Import IP Geolocation Data

Download a public IP geolocation CSV file.

Upload it into Sentinel as a Watchlist.

This allows IP-to-country correlation.



13. Enrich Logs with Geolocation Data

Modify KQL queries to:

Match attacker IPs with the watchlist

Identify country of origin

Validate successful enrichment.



14. Create a Sentinel Map Visualization

Build a Sentinel workbook.

Create a map visualization showing:

Attacker source countries

Frequency of login attempts

Confirm data renders correctly on the map.



15. Review and Clean Up

Analyze attack patterns and geographic trends.

Stop or delete resources to avoid ongoing Azure costs.

Outcome

Built a cloud-based SOC lab

Collected real attack telemetry

Used KQL for detection

Visualized attacker locations in Microsoft Sentinel
