# Cloud-SOC-Lab-Step-by-Step-Guide-Azure-Microsoft-Sentinel-

# Project Lab:

This Lab walks you through setting up a cloud-based home SOC lab using Microsoft Azure and Microsoft Sentinel. It shows how to build and configure a basic Security Operations Center environment in the cloud — including creating a resource group and virtual network, deploying a VM, configuring logging and log ingestion, and visualizing security events. The tutorial is aimed at helping learners get hands-on experience with SIEM concepts and real-world tooling for monitoring and detecting threats.

Reference Josh Madakor's Guide: https://www.youtube.com/watch?v=g5JL2RIbThM&t=1186s<br><br><br><br>



1. Create an Azure Account

Sign up for an Azure account (free tier is sufficient).

Confirm billing and access the Azure Portal.<br><br><br><br>
<img width="1541" height="901" alt="Screenshot 2026-02-16 181211" src="https://github.com/user-attachments/assets/de51010b-84c0-445d-b037-b6be2be4c7ca" />



2. Create a Resource Group

In the Azure Portal, create a Resource Group.

Choose a region close to your location.

This will contain all lab resources.<br><br><br><br>
<img width="993" height="316" alt="Screenshot 2026-02-16 181352" src="https://github.com/user-attachments/assets/17ecdc35-a866-4d1b-a24f-b107b8d2112e" />
<img width="804" height="454" alt="Screenshot 2026-02-16 181522" src="https://github.com/user-attachments/assets/362bb191-d0ee-42aa-a9f6-f4b9cf7d3d2b" />
<img width="737" height="856" alt="Screenshot 2026-02-16 181620" src="https://github.com/user-attachments/assets/3a02d347-277c-4202-b704-36fec2a097ed" />
<img width="569" height="830" alt="Screenshot 2026-02-16 181716" src="https://github.com/user-attachments/assets/ab833972-0a76-411a-8cb1-5e61be65aa19" />



3. Create a Virtual Network and Deploy a Virtual Machine

Create a Windows Virtual Machine.

Assign it to the resource group.

Enable public IP access.

Set a username and password for RDP access.<br><br><br><br>
<img width="934" height="681" alt="Screenshot 2026-02-16 182447" src="https://github.com/user-attachments/assets/71bcd940-430b-4540-9e62-d62852880151" />
<img width="712" height="646" alt="Screenshot 2026-02-16 182613" src="https://github.com/user-attachments/assets/cf63c04d-e1ac-4874-9b88-d984039d0b07" />
<img width="780" height="805" alt="Screenshot 2026-02-16 182701" src="https://github.com/user-attachments/assets/12099fc3-0b9e-425d-82a6-77f5348a4841" />
<img width="728" height="805" alt="Screenshot 2026-02-16 182841" src="https://github.com/user-attachments/assets/9459ee67-f76a-40e4-aa7c-74448ae6b8c7" />
<img width="728" height="805" alt="Screenshot 2026-02-16 182848" src="https://github.com/user-attachments/assets/3f846abb-02c3-4389-a956-cb09242e2695" />
<img width="531" height="812" alt="Screenshot 2026-02-16 183000" src="https://github.com/user-attachments/assets/fc78c225-1f25-4e1d-b887-2e2574d07236" />
<img width="778" height="511" alt="Screenshot 2026-02-16 183109" src="https://github.com/user-attachments/assets/21e6fb41-ab58-4cb1-89de-fb6d3642672b" />
<img width="711" height="411" alt="Screenshot 2026-02-16 183134" src="https://github.com/user-attachments/assets/fe6d2c10-56d9-41f2-b7b6-f25de124e381" />
<img width="911" height="798" alt="Screenshot 2026-02-16 183258" src="https://github.com/user-attachments/assets/a2899d2a-3cf5-4124-b7e3-c8108758a67f" />
<img width="812" height="290" alt="Screenshot 2026-02-16 183332" src="https://github.com/user-attachments/assets/317e0dcb-f783-40f7-87d6-a52cfc9b827a" />
<img width="902" height="725" alt="Screenshot 2026-02-16 183531" src="https://github.com/user-attachments/assets/1b8ca43b-8488-47a4-ba6f-80805ceb6b2d" />
<img width="738" height="435" alt="Screenshot 2026-02-16 183549" src="https://github.com/user-attachments/assets/1cecfb0f-76aa-4786-85e6-f07420e3790a" />
<img width="931" height="776" alt="Screenshot 2026-02-16 183634" src="https://github.com/user-attachments/assets/a3f4aa79-1e99-47a8-9684-5b4761cae638" />
<img width="941" height="790" alt="Screenshot 2026-02-16 183758" src="https://github.com/user-attachments/assets/734c1e75-69c6-44a4-982b-609bfbb20aba" />
<img width="757" height="542" alt="Screenshot 2026-02-16 183817" src="https://github.com/user-attachments/assets/07b94768-f3c0-4498-b674-05ed33b2a6dc" />
<img width="906" height="772" alt="Screenshot 2026-02-16 183844" src="https://github.com/user-attachments/assets/a5b16663-19fc-486c-ac8b-060314813b09" />
<img width="916" height="796" alt="Screenshot 2026-02-16 184020" src="https://github.com/user-attachments/assets/393783c7-82c0-4844-b3d9-eedd95a27dc9" />



4. Expose the VM to the Internet (Intentionally)

Open the Network Security Group (NSG) attached to the VM.

Allow inbound traffic on:

RDP (Port 3389) from any source.

This makes the VM intentionally vulnerable to attract brute-force attempts.<br><br><br><br>



5. Disable Windows Firewall (Lab Purpose Only)

RDP into the VM.

Disable Windows Defender Firewall.

This ensures logs capture more visible activity.

⚠️ This is for lab learning only, not production use.<br><br><br><br>



6. Verify Security Event Logging

On the VM, open Event Viewer.

Confirm Security logs are being generated (especially failed login attempts).<br><br><br><br>



7. Create a Log Analytics Workspace

In Azure, create a Log Analytics Workspace.

Associate it with the same resource group.

This workspace will store all security logs.<br><br><br><br>



8. Enable Microsoft Sentinel

Open Microsoft Sentinel in Azure.

Attach it to the Log Analytics Workspace.

Sentinel now acts as the SIEM for the lab.<br><br><br><br>



9. Connect the VM to Sentinel

In Sentinel, enable the Windows Security Events data connector.

Configure it to collect All Security Events.

Verify logs begin appearing in the workspace.<br><br><br><br>



10. Generate Real Attack Data

Leave the VM exposed for several hours.

Allow real-world attackers to attempt RDP logins.

Failed login attempts will populate Sentinel logs.<br><br><br><br>



11. Query Logs Using KQL

Open Logs in Microsoft Sentinel.

Run KQL queries to analyze:

Failed login attempts

Source IP addresses

Event IDs (e.g., 4625)

Confirm real attack data is visible.<br><br><br><br>



12. Import IP Geolocation Data

Download a public IP geolocation CSV file.

Upload it into Sentinel as a Watchlist.

This allows IP-to-country correlation.<br><br><br><br>



13. Enrich Logs with Geolocation Data

Modify KQL queries to:

Match attacker IPs with the watchlist

Identify country of origin

Validate successful enrichment.<br><br><br><br>



14. Create a Sentinel Map Visualization

Build a Sentinel workbook.

Create a map visualization showing:

Attacker source countries

Frequency of login attempts

Confirm data renders correctly on the map.<br><br><br><br>



15. Review and Clean Up

Analyze attack patterns and geographic trends.

Stop or delete resources to avoid ongoing Azure costs.

Outcome

Built a cloud-based SOC lab

Collected real attack telemetry

Used KQL for detection

Visualized attacker locations in Microsoft Sentinel
