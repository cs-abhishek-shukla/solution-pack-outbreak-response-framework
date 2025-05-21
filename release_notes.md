## What's New

>[!NOTE]
>This solution pack requires FortiSOAR `v7.6.1` and later.

### Enhanced Performance of Threat Intel Feed Ingestion

Experience a significant boost in performance during the ingestion of Threat Intel Feeds for Outbreak Alerts:

**Bulk Ingestion**: The individual IOC creation process in playbooks has been replaced with a Bulk Ingestion step. This enhancement leverages a connector action to trigger a bulk ingestion playbook that batches IOCs into groups and processes them asynchronously. This approach ensures faster and more efficient processing of threat intelligence feeds.

### Experience Enhancements

- **Navigation menu update**
  - The **Outbreak Management** menu now features a brand new icon![](./docs/res/icon-outbreak.svg).
  - Outbreak Management no longer has the hunt rules and dashboard tabs.

- **Dashboard Enhancements**
  - Outbreak Response Framework now has a dedicated dashboard that can be launched from the **Outbreak Management** menu.
  - The dashboard now showcases a new data representation &ndash; *Outbreak by Severity (Last 30 days)*.

- **Simplified Alert Details**
  - Hunt rules now appear under a separate tab on the outbreak alert details page.

### Wizard Enhancements

- **Configure Integrations**
  - NIST National Vulnerability Database connector configuration is optional now.
  - Wizard now also verifies whether the **Mark as Default Configuration** option has been selected for all chosen integrations.

### Automated Updates for Outbreak Alerts

A new feature automatically updates critical information for Outbreak Alerts with the statuses *New* or *Tracking*. This is achieved using the **Update Outbreak Alert Details** playbook, which updates key details such as CVEs, background information, and descriptions. The playbook is scheduled to run daily, ensuring that alerts remain current and accurate.

### Fields Mapping in Threat Intel Feeds

- Updated the mapping of the *Type* field in Threat Intel Feeds to accurately reflect the specific hash type (*`FileHash-MD5`*, *`FileHash-SHA1`*, and *`FileHash-SHA256`*) instead of using the generic type *`FileHash`*.

### Enhanced CVE Details with EPSS Scores

The following fields have been mapped into CVE records to provide enhanced threat context:  

- `EPSS Score`
- `EPSS Percentile`
- `Known To Be Used In Ransomware Campaigns`

### NIST NVD Connector Action Isolation

The **NIST NVD Connector** action, responsible for fetching CVE details, has been isolated into a dedicated playbook named **Update CVE Details from NIST**. This playbook includes the setting `Ignore Error` set to *Yes* to handle intermittent API issues more gracefully.  

The **Update CVE Details from NIST** playbook is referenced as the final step in the **Find Known Exploited Vulnerabilities (KEV) CVEs** playbook. This change addresses the intermittent reliability issues with the NIST NVD APIs and ensures uninterrupted processing of CVE data.

Refer to the section [Retrieving CVE Information from NIST](./docs/usage.md#retrieving-cve-information-from-nist) to learn how to update this information manually.

### Key Store Enhancements

- Key Store records associated with Outbreaks are now tagged with **`Outbreak Alert`**

### Schedule Changes for Solution Pack Deployment

The crontab schedule for **Outbreak_Automated-Deployment-Outbreak-Alert-Response-Solution-Pack** has been adjusted to run **every 3 hours**. This ensures the timely deployment of new outbreak alert solution packs.  

These solution packs, created upon receiving outbreak alerts from FortiGuard, include YARA rules, Sigma rules, and other detection mechanisms designed to facilitate the hunting and identification of outbreaks within a network.

### Playbook Enhancements and Cleanups

- **Investigate Outbreak**
  - The playbook has been optimized to remove redundancy.
  - The limit on fetching and investigating IoC records has been removed. Now all IOCs linked with Outbreak Alert are fetched and investigated.

- **Retrieve CVEs and IOCs**
  - The step *Investigate Outbreak Alert* has been renamed to **Ingest Outbreak CVEs and IOCs Details** to better convey its functionality.
