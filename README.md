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
<img width="884" height="658" alt="Screenshot 2026-02-16 184156" src="https://github.com/user-attachments/assets/5de8c5d6-2eb9-4a64-b3db-f0cf17c298d2" />
<img width="1570" height="671" alt="Screenshot 2026-02-16 184328" src="https://github.com/user-attachments/assets/c3495f6c-5ebe-41ec-bc60-1a55eee269c0" />
<img width="578" height="591" alt="Screenshot 2026-02-16 184414" src="https://github.com/user-attachments/assets/459fa20c-dc5a-4c11-84ba-1540f932b894" />
<img width="1564" height="798" alt="Screenshot 2026-02-16 184501" src="https://github.com/user-attachments/assets/31563d81-58c4-45a9-b755-20c6a8030bde" />
<img width="576" height="697" alt="Screenshot 2026-02-16 184558" src="https://github.com/user-attachments/assets/c5492ff1-7f1b-48e5-86a3-a921dfb94f97" />



5. Disable Windows Firewall (Lab Purpose Only)

RDP into the VM.

Disable Windows Defender Firewall.

This ensures logs capture more visible activity.

⚠️ This is for lab learning only, not production use.<br><br><br><br>
<img width="1546" height="515" alt="Screenshot 2026-02-16 184814" src="https://github.com/user-attachments/assets/9900e0aa-b055-4aa8-a0e1-459fb81d8683" />
<img width="1546" height="515" alt="Screenshot 2026-02-16 184821" src="https://github.com/user-attachments/assets/f14ed955-f398-4a93-b0fa-0ea7d2bb8b22" />
<img width="693" height="783" alt="Screenshot 2026-02-16 185037" src="https://github.com/user-attachments/assets/aa6254ed-abb6-4ed3-b38e-f9fee2200ed2" />
<img width="435" height="258" alt="Screenshot 2026-02-16 185138" src="https://github.com/user-attachments/assets/9de3871d-8854-4b7e-9dd8-db49480b8035" />
<img width="447" height="261" alt="Screenshot 2026-02-16 185259" src="https://github.com/user-attachments/assets/b0fac199-84c1-438a-bcd1-9a730d8da716" />
<img width="394" height="220" alt="Screenshot 2026-02-16 185332" src="https://github.com/user-attachments/assets/307650a2-4670-466b-b776-f629edfac2da" />
<img width="797" height="622" alt="Screenshot 2026-02-16 185453" src="https://github.com/user-attachments/assets/38fd646b-3fda-4ef5-9621-52e58e2a48b4" />
<img width="1276" height="952" alt="Screenshot 2026-02-16 185553" src="https://github.com/user-attachments/assets/540ce1f8-c2ee-4896-9b45-95badb61345a" />
<img width="675" height="602" alt="Screenshot 2026-02-16 185636" src="https://github.com/user-attachments/assets/b0e42d58-73f3-400a-b16e-bc1bc45bdfba" />
<img width="484" height="300" alt="Screenshot 2026-02-16 185704" src="https://github.com/user-attachments/assets/6905a2ac-9f2d-4458-b9de-bd317d2b9b3c" />
<img width="545" height="296" alt="Screenshot 2026-02-16 185721" src="https://github.com/user-attachments/assets/4424394c-e75c-4699-9198-749f4971c9a8" />
<img width="548" height="566" alt="Screenshot 2026-02-16 185738" src="https://github.com/user-attachments/assets/9cab564f-7e43-4ee8-bba6-41715f8b527c" />



6. Verify Security Event Logging

On the VM, open Event Viewer.

Confirm Security logs are being generated (especially failed login attempts).<br><br><br><br>
<img width="518" height="437" alt="Screenshot 2026-02-19 160044" src="https://github.com/user-attachments/assets/43a4bf9d-dd89-4b22-81a7-f92641c1e1fd" />
<img width="341" height="229" alt="Screenshot 2026-02-19 160101" src="https://github.com/user-attachments/assets/c4998331-9927-4211-b8b5-a397c1a46f29" />
<img width="905" height="476" alt="Screenshot 2026-02-19 160208" src="https://github.com/user-attachments/assets/767ab98a-4742-47c6-90dc-84c4709992fd" />



7. Create a Log Analytics Workspace

In Azure, create a Log Analytics Workspace.

Associate it with the same resource group.

This workspace will store all security logs.<br><br><br><br>
<img width="1128" height="338" alt="Screenshot 2026-02-19 160321" src="https://github.com/user-attachments/assets/50e25ea0-b0e5-4290-a551-7a94a144cc4e" />
<img width="810" height="509" alt="Screenshot 2026-02-19 160340" src="https://github.com/user-attachments/assets/8618afe5-b216-415b-961a-69bfc6b605ec" />
<img width="729" height="814" alt="Screenshot 2026-02-19 160430" src="https://github.com/user-attachments/assets/7be19af0-5257-43f6-9ab9-1755027ad488" />
<img width="773" height="806" alt="Screenshot 2026-02-19 160531" src="https://github.com/user-attachments/assets/8d5f3611-003b-4d2a-af9c-fd25fee7d9ca" />



8. Enable Microsoft Sentinel

Open Microsoft Sentinel in Azure.

Attach it to the Log Analytics Workspace.

Sentinel now acts as the SIEM for the lab.<br><br><br><br>
<img width="1107" height="340" alt="Screenshot 2026-02-19 160626" src="https://github.com/user-attachments/assets/d964fcc8-b699-4da0-81f0-5998a06073c5" />
<img width="664" height="395" alt="Screenshot 2026-02-19 160640" src="https://github.com/user-attachments/assets/cea8b11c-c8c1-4f43-82fc-0ca8dc3bd28e" />
<img width="892" height="804" alt="Screenshot 2026-02-19 160714" src="https://github.com/user-attachments/assets/6fdae323-b7f6-4120-b1ac-acf4fbc2c2ea" />
<img width="1429" height="600" alt="Screenshot 2026-02-19 160821" src="https://github.com/user-attachments/assets/1f96b48c-ecb6-481d-acb3-91fb9cab5757" />
<img width="1231" height="594" alt="Screenshot 2026-02-19 160947" src="https://github.com/user-attachments/assets/add85caf-7712-4fee-b7b7-11df128d7bcb" />
<img width="1189" height="620" alt="Screenshot 2026-02-19 161020" src="https://github.com/user-attachments/assets/b3928e64-0ea6-4b11-9f28-eb735a089a8c" />
<img width="1189" height="620" alt="Screenshot 2026-02-19 161027" src="https://github.com/user-attachments/assets/1ca7e607-b5a3-41a0-a768-64582b792ee3" />
<img width="1275" height="610" alt="Screenshot 2026-02-19 161112" src="https://github.com/user-attachments/assets/6f22c80a-e3c7-4d31-93fb-0a593750b5d7" />
<img width="1234" height="418" alt="Screenshot 2026-02-19 161209" src="https://github.com/user-attachments/assets/d1e043b6-f3fe-4cb9-84cb-f9072a5b6da0" />
<img width="1189" height="453" alt="Screenshot 2026-02-19 161338" src="https://github.com/user-attachments/assets/dec0d159-0148-4207-a088-cf49e9202cbb" />



9. Connect the VM to Sentinel

In Sentinel, enable the Windows Security Events data connector.

Configure it to collect All Security Events.

Verify logs begin appearing in the workspace.<br><br><br><br>
<img width="959" height="570" alt="Screenshot 2026-02-19 161445" src="https://github.com/user-attachments/assets/409afdcd-fdfb-43b1-9b27-5f1c33c04de3" />
<img width="1132" height="666" alt="Screenshot 2026-02-19 161522" src="https://github.com/user-attachments/assets/f38c4d3a-acef-4661-baa2-224a5471eb8a" />
<img width="781" height="804" alt="Screenshot 2026-02-19 161635" src="https://github.com/user-attachments/assets/64cfbf48-cf67-45d0-b533-9eec12d50f9c" />
<img width="866" height="807" alt="Screenshot 2026-02-19 161710" src="https://github.com/user-attachments/assets/74391e3d-05ce-40eb-b1c6-7fe395faa390" />
<img width="609" height="815" alt="Screenshot 2026-02-19 161816" src="https://github.com/user-attachments/assets/3a3d2b0b-5deb-4dc6-b642-4129039cfefc" />
<img width="585" height="809" alt="Screenshot 2026-02-19 161844" src="https://github.com/user-attachments/assets/d1599a28-174b-4c1f-9f9a-5671158d1c50" />
<img width="1563" height="628" alt="Screenshot 2026-02-19 162029" src="https://github.com/user-attachments/assets/7f482dce-e219-4c04-a709-7459c24fde19" />
<img width="1565" height="539" alt="Screenshot 2026-02-19 162249" src="https://github.com/user-attachments/assets/ee013f00-5b7b-4712-8fc2-78e663929a0b" />



10. Generate Real Attack Data

Leave the VM exposed for several hours.

Allow real-world attackers to attempt RDP logins.

Failed login attempts will populate Sentinel logs.<br><br><br><br>
<img width="1558" height="885" alt="Screenshot 2026-02-19 162401" src="https://github.com/user-attachments/assets/f2115d40-8e74-4bfa-af0f-6fdc6f371fc5" />



11. Query Logs Using KQL

Open Logs in Microsoft Sentinel.

Run KQL queries to analyze:

Failed login attempts

Source IP addresses

Event IDs (e.g., 4625)

Confirm real attack data is visible.<br><br><br><br>
<img width="1491" height="772" alt="Screenshot 2026-02-19 184827" src="https://github.com/user-attachments/assets/15433e90-55c1-4361-b8ee-030ed0f20bbe" />
<img width="1506" height="749" alt="Screenshot 2026-02-19 184920" src="https://github.com/user-attachments/assets/93b6e81c-5b48-4f83-b7d9-5b706726036d" />
<img width="1530" height="784" alt="Screenshot 2026-02-19 185038" src="https://github.com/user-attachments/assets/90f4837d-3143-4b48-a75e-1180d3aee8ca" />



12. Import IP Geolocation Data

Download a public IP geolocation CSV file.

Upload it into Sentinel as a Watchlist.

This allows IP-to-country correlation.<br><br><br><br>
<img width="563" height="908" alt="Screenshot 2026-02-19 185439" src="https://github.com/user-attachments/assets/cb9e11c8-d7b0-412f-aba1-a68fff08f784" />
<img width="1572" height="789" alt="Screenshot 2026-02-19 185617" src="https://github.com/user-attachments/assets/968ec3eb-e234-4f49-a498-d655d6dc3ade" />
<img width="795" height="820" alt="Screenshot 2026-02-19 185730" src="https://github.com/user-attachments/assets/be3bab70-3fc4-4046-a792-6450298073c3" />
<img width="1569" height="810" alt="Screenshot 2026-02-19 185810" src="https://github.com/user-attachments/assets/085edfe2-ff5f-44b6-a624-bfcf7cea3c7f" />
<img width="1564" height="809" alt="Screenshot 2026-02-19 185923" src="https://github.com/user-attachments/assets/ab326d71-1ece-4e4b-acd8-dd4dc44d5f93" />
<img width="1567" height="818" alt="Screenshot 2026-02-19 190051" src="https://github.com/user-attachments/assets/c7248b91-a223-4b7d-8b07-54bff30c08ea" />



13. Enrich Logs with Geolocation Data

Modify KQL queries to:

Match attacker IPs with the watchlist

Identify country of origin

Validate successful enrichment.<br><br><br><br>
<img width="1564" height="804" alt="Screenshot 2026-02-19 190224" src="https://github.com/user-attachments/assets/beed07ec-0f16-4664-aa44-a3a591a62df3" />
<img width="1568" height="377" alt="Screenshot 2026-02-19 190327" src="https://github.com/user-attachments/assets/90f7719b-9245-4c4e-8088-dbb845848c61" />
<img width="1535" height="790" alt="Screenshot 2026-02-19 190410" src="https://github.com/user-attachments/assets/292c31e0-7e7f-4c66-a90c-76ccee91d28b" />



14. Create a Sentinel Map Visualization

Build a Sentinel workbook by pasting the .json text into the workbook.

Create a map visualization showing:

Attacker source countries

Frequency of login attempts

Confirm data renders correctly on the map.<br><br><br><br>
<img width="1354" height="515" alt="Screenshot 2026-02-19 190548" src="https://github.com/user-attachments/assets/2d8b104a-2d10-4152-8dba-a908ee6e880c" />
<img width="1278" height="764" alt="Screenshot 2026-02-19 190617" src="https://github.com/user-attachments/assets/8af5de4d-2f9c-4f1e-8446-272b5b32d6d7" />
<img width="974" height="491" alt="Screenshot 2026-02-19 190650" src="https://github.com/user-attachments/assets/70bd1188-527b-4cf0-b1fb-46513faa2ac4" />
<img width="1482" height="575" alt="Screenshot 2026-02-19 190717" src="https://github.com/user-attachments/assets/71d6c12a-a1ac-44af-bd47-935d2bdcb5de" />
<img width="1568" height="730" alt="Screenshot 2026-02-19 190758" src="https://github.com/user-attachments/assets/8bfa3736-9003-4507-845e-e643e3dfe811" />
<img width="1549" height="478" alt="Screenshot 2026-02-19 190836" src="https://github.com/user-attachments/assets/2e9f2782-fd76-4b96-a231-3fd4beaecaf1" />
<img width="1702" height="865" alt="Screenshot 2026-02-19 190935" src="https://github.com/user-attachments/assets/67cd5b03-dea5-4e4d-a025-25e3174f9b9f" />
<img width="745" height="641" alt="Screenshot 2026-02-19 191029" src="https://github.com/user-attachments/assets/b9bb72d6-7bf7-4d88-b261-830ae4933019" />
<img width="823" height="779" alt="Screenshot 2026-02-19 191111" src="https://github.com/user-attachments/assets/30d8b328-eb9c-47ef-b9a3-35f65347c231" />
<img width="803" height="773" alt="Screenshot 2026-02-19 191146" src="https://github.com/user-attachments/assets/b44ff119-d142-4fc9-9aad-a0cb5bc0686d" />
<img width="1556" height="812" alt="Screenshot 2026-02-19 191241" src="https://github.com/user-attachments/assets/08c522bf-ce7f-4e2f-b38e-447cb803b569" />
<img width="1542" height="765" alt="Screenshot 2026-02-19 191546" src="https://github.com/user-attachments/assets/e467be27-b3de-461f-a23c-3aac50829110" />
<img width="1579" height="766" alt="Screenshot 2026-02-19 191630" src="https://github.com/user-attachments/assets/5b5701ef-55a4-4f8c-a741-47d9dbf21ed0" />


