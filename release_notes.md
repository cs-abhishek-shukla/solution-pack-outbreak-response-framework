## What's New

> [!NOTE]
> This solution pack requires FortiSOAR `v7.6.4` and later.

### Enhancements

- **Threat Intel Dashboards Integrated**: These dashboards contain outbreak and threat intelligence data, making them more relevant when included directly in the **Outbreak Response Framework**. Analysts can now have a consolidated view of outbreak intelligence without needing to switch contexts:
  - Threat Intel Overview
  - Threat Intel Insights Report

- **Expanded Threat Actor Correlation**

  - The **Get Outbreak Alert Threat Actors and Link Threat Reports** playbook now establishes a many-to-many relationship with the **Threat Actor** module ensuring outbreak alerts are enriched with deeper adversary context, enabling analysts to quickly see which actors are associated with which reports and alerts.

### Fixes

- **Threat Actor - Outbreak Alert Correlation**

  - Fixed missing reverse mapping between **Threat Intel Reports** and **Outbreak Alerts**.for bidirectional visibility, so analysts can trace both from an outbreak alert to related Threat Actor information and back to its associated outbreak.

- **Comprehensive Report Correlation**

  - Updated correlation logic so **Outbreak Alerts** are now linked with all relevant report types, including **FortiGuard Outbreak Alerts**, not just **Threat Signal Reports** giving analysts full coverage of outbreak intelligence, preventing gaps when different report types are ingested.

- **Investigate Outbreak Alerts Schedule**

  - Fixed an issue where the updated investigation frequency was not saved in the `Investigate_Outbreak-Alerts` schedule.

- Fixed an issue where Outbreak Installation playbooks were failing intermittently.
