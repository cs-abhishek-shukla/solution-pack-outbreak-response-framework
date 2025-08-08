## What's New

>[!NOTE]
>This solution pack requires FortiSOAR `v7.6.1` and later.

Enhance your outbreak response playbook with expanded threat context, smarter automation, and fine-tuned control—delivered in the latest update to the Outbreak Response Framework.

---

### Wizard Enhancements

- Additional options on the **Installation & Notification** screen:
  - You can specify the time window for fetching and installing recent outbreak response solution packs &mdash; streamlining automation and reducing noise from outdated threats.

  - You can also choose to install all outbreak response solution packs released to date, providing full historical coverage when needed.

- The wizard now supports configuring the connector on an agent.

---

### Dashboard Enhancements

In the **Outbreak Response Overview** dashboard

- Removed the Outbreak Trend chart to streamline visual focus.
- Updated the Recent Outbreaks Detected chart:
  - Added new data columns for better visibility.
  - Reorganized the order and resized column lengths for improved readability.

---

### Expanded Field Coverage

Introduced two new fields for enriched mapping of FortiGuard Labs data:

- **Threat Actors**: Map adversaries linked to the outbreak.
- **Threat Reports**: Reference original threat research or campaign details.

---

### New Automation Actions

- **Fetch Latest CVEs and IOC Details**: In List View, this new action updates **all outbreak alerts** with status `New` or `Tracking` by pulling the latest:

  - CVE entries (including KEV mapping)
  - IOC intelligence

- **Fetch and Update Outbreak Alert Details**: Available when alerts are selected, this action performs a focused update on the selected outbreak alerts.

---

### Improved Detail View Experience

A new **Summary** tab centralizes critical alert information like:

- Description, Background, and Severity
- CVE and IOC details
- FortiGuard URL and Cybersecurity Framework alignment
- Threat Actors mapped via FortiGuard Labs

---

### Playbook Enhancements

- A new playbook **Get Outbreak Alert Threat Actors and Link Threat Reports** automatically associates alerts with threat actors and relevant reports, installs required response packs, and syncs updated data.

- The following playbooks have been renamed for more clarity on their intended actions:
  - *Outbreak Alert Time Frame Analysis* has been renamed to **Deactivate Expired Outbreak Alerts**
  - *Update Outbreak Alert Details* has been renamed to **Fetch and Update Outbreak Alert Details**
  - *Tracking Outbreak: Retrieve CVEs and IOCs* has been renamed to **Fetch and Update Active Outbreak Alerts CVEs and IOCs**                     |
  - *Find Known Exploited Vulnerabilities (KEV) CVEs* has been renamed to **Link or Create CVEs**
  - *> Automated Deployment > Get Outbreak CVEs and IOC Details* has been renamed to **> Automated Deployment > Get Outbreak CVEs IOCs and Threat Actors Details**

#### Cleanup and Improvements

- **Deprecated**: The `Update CVE Details from NIST` playbook has been removed.
- **Manual trigger**: The `Fetch and Update Outbreak Alert Details` now starts manually.
- **Schedule removed**: The `Outbreak_Alert_Fetch_Latest_Details` schedule has been removed and now handled via a configuration automation

---

### Schedule & Framework Updates

- The following schedules have been renamed:
  - *`Outbreak_Alert_Fetch_Latest_Details`* has been renamed to **Ingestion_Fetch-and-Update-Outbreak-Alert-Latest-Details**
  - *`Outbreak_Automated-Deployment-Outbreak-Alert-Response-Solution-Pack`* has been renamed to **Ingestion_Outbreak-Alert-Response-Solution-Pack**
  - *`Outbreak_Alert-Time-Frame-Analysis`* has been renamed to **Deactivate-Expired-Outbreak-Alerts**
  - *`Outbreak_Ingest-Tracking-Outbreak-CVEs-and-IOCs`* has been renamed to **Ingestion_Outbreak-Alert-Latest-CVEs-and-IOCs-Details**

- The **Configure Outbreak Response Framework** playbook now performs the following tasks:

- Triggers **Ingest Known Exploited Vulnerabilities (KEV) CVEs**
- Activates `Investigate_Outbreak-Alerts` (now inactive by default post-install)
- Creates the following automation schedules:

  - `Ingestion_Fetch-and-Update-Outbreak-Alert-Latest-Details`
  - `Ingestion_Outbreak-Alert-Response-Solution-Pack`
  - `Ingestion_Outbreak-Alert-Latest-CVEs-and-IOCs-Details`
  - `Deactivate-Expired-Outbreak-Alerts`

---

With this update, SOC teams can respond faster to outbreaks by working with **real-time vulnerability and threat actor intelligence**, directly from FortiGuard Labs. Save time. Reduce noise. Improve context.