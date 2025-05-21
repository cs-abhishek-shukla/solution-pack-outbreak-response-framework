| [Home](../README.md) |
| -------------------- |

# Contents

The **Outbreak Response Framework** solution pack contains the following resources.

## Picklist

| Name                    | Description                                                                                                 |
|:------------------------|-------------------------------------------------------------------------------------------------------------|
| Outbreak Alert Severity | List of outbreak severity item values (Medium, High and Critical)                                           |
| Threat Hunt Tools       | List of Threat Hunt Integration item value which will used for Threat Hunting                               |
| Threat Hunt Rule Type   | (Previously *Rule Type*) List of Outbreak Alert Threat Hunt Rule item values (Yara, Sigma, Fortinet Fabric) |
| Outbreak Alert Status   | (Previously *Record Status*) List of Outbreak Alert status item value(Active, Resolved)                     |
| IncidentType            | List of items containing the possible incident types as list items (E.g. Beaconing, Brute Force Attempts)   |

## Record Sets

| Name                                      | Description                                                                                                                                                                                           |
|:------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `outbreak-threat-hunt-tools`              | Saves the names of outbreak hunt tools, like FortiSIEM, FortiAnalyzer, etc., and helps the outbreak configuration wizard to select the required tools.                                                |
| `outbreak-auto-install-time-frame`        | Saves the number of days for which the outbreak-specific response solution packs are set to install during configuration.                                                                             |
| `outbreak-threat-hunt-tools-params`       | Saves the outbreak hunt tools parameters, like ADOM name for FortiAnalyzer and `splunk_index` for Splunk, and helps the outbreak configuration wizard to populate these parameters.                   |
| `outbreak-alert-config`                   | Saves the configuration parameters provided at the time of framework configuration, like `huntTools`, `installOutbreakType`, `emailAddress`, etc, helping in outbreak installation and investigation. |
| `outbreak-threat-hunting-workflow-config` | This Key Store stores the values of IOC, Fortinet Fabric, and Signature Hunting tools along with their associated parameters.                                                                         |

## Module Schema

| Name              | Description                                                       |
|:------------------|:------------------------------------------------------------------|
| Threat Hunt Rules | A module that list the Yara, Sigma and Fortinet Fabric Hunt Rules |
| Outbreak Alerts   | A module that list the outbreak details                           |

## Connector

| Name                                                           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|:---------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Fortinet FortiAnalyzer                                         | FortiAnalyzer is the NOC-SOC security analysis tool built with operations perspective. With action-oriented views and deep drill-down capabilities, FortiAnalyzer not only gives organizations critical insight into threats, but also accurately scopes risk across the attack surface, pinpointing where immediate response is required.                                                                                                               |
| Fortinet FortiSIEM                                             | FortiSIEM provides integrations that allow you to query and make changes to the CMDB, query events, and send incident notifications. Provide actions like get incidents, comment incident, cleared incident, get device details, get monitored organizations, report related actions and get all associated events for an incident from FortiSIEM.                                                                                                       |
| Fortinet FortiGuard Outbreak                                   | Fortinet FortiGuard Outbreak connector receives communication from *FortiGuard Outbreak Alerts* regarding an outbreak and its details. These alerts help understand the technical details of the attack and how organizations can protect themselves from the attack and others like it.                                                                                                                                                                 |
| IBM QRadar                                                     | IBM QRadar is an enterprise security information and event management (SIEM) product. Fortinet FortiSOSR connector for IBM QRadar allows user to invoke QRadar API, perform Ariel Queries and operations like Get Offense,related events,update and close offenses.                                                                                                                                                                                      |
| NIST National Vulnerability Database                           | The NIST National Vulnerability Database (NVD) is the U.S. government repository of standards based vulnerability management data represented using the Security Content Automation Protocol (SCAP). This data enables automation of vulnerability management, security measurement, and compliance. The NVD includes databases of security checklist references, security related software flaws, misconfigurations, product names, and impact metrics. |
| Splunk                                                         | Splunk connector allows users to invoke search, fetch events to related search, invoke alert actions, update notables, sync splunk users to FortiSOAR etc.                                                                                                                                                       

## Widgets

| Name                                                | Description                                                                                                                                                                                                                   |
|:----------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Outbreak Response Framework Configuration Wizard    | Outbreak Response Framework Configuration Wizard has options to select the Threat Detection Integrations sources to run outbreak response hunt activities as part of your response or threat management strategy in FortiSOAR |
| Playbook Execution Wizard![new](./res/icon-new.svg) | The Playbook Execution Wizard widget renders playbook execution logs and related comments on the wizard                                                                                                                       |
| Playbook Buttons![new](./res/icon-new.svg)          | The Playbook Buttons widget creates playbook buttons on a records detailed view                                                                                                                                               |

## Roles

| Name                 | Description                                                                                                        |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------|
| Full App Permissions | Essentially the root user, use carefully                                                                           |
| SOC Manager          | Responsible for Incident Investigation and other remediation and containment-related tasks.                        |
| SOC Analyst          | Responsible for Alert Triages, false-positive filtering, and escalating potentially malicious alerts to Incidents. |

## Playbook Collection

| 10 - SP - Outbreak Response Framework |
|:-------------------------------------:|


| Playbook Name                                                                       | Description                                                                                                                                     |
|:------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------|
| > Automated Deployment > Get Outbreak CVEs and IOC Details                          | Retrieve Outbreak CVEs and IOC details, and set the last investigation time for newly installed outbreak alerts.                                |
| > Investigate Outbreak Alert                                                        | Investigate the Outbreak Alert using various threat-hunting tools to understand the scope and impact of the threat                              |
| Automated Deployment: Outbreak Alert Response Solution Pack                         | Automate Installation of Recent Outbreak Alert Solutions Pack (Last x Days) with Email Notification                                             |
| Bulk Ingest Outbreak Alert IOCs ![new](./res/icon-new.svg)                          | Bulk Ingest Outbreak Alert IOCs on the basis of Outbreak Tag                                                                                    |
| Configure Outbreak Response Framework                                               | Set up the outbreak response framework, configure global value key store entries, and set up schedules for use in outbreak investigations.      |
| Create IOCs as Threat Intel Feeds                                                   | Obtain the IOCs from Fortinet FortiGuard and create the threat feeds in the Threat Intel module for the specified outbreak alert.               |
| Find and Link Affected Assets                                                       | Examine vulnerabilities associated with the outbreak CVEs, and if any are found, identify the affected assets and link them to the outbreak.    |
| Find Known Exploited Vulnerabilities (KEV) CVEs                                     | Fetch Known Exploited Vulnerabilities (KEV) CVEs from NIST and create CVE record.                                                               |
| Get Outbreak CVEs and IOCs Details                                                  | Obtain outbreak alert CVE details from NIST and IOC information from Fortinet FortiGuard.                                                       |
| Investigate Outbreak                                                                | Investigate the Outbreak Alert using various threat-hunting tools to understand the scope and impact of the threat                              |
| Investigate Outbreaks (Type All)                                                    | Investigate New and Tracking outbreaks across various SIEM tools, then take action to remediate and mitigate them.                              |
| Link Related Threat Intel Feeds ![new](./res/icon-new.svg)                          | This playbook links the unlinked Threat Intel Feeds to the Outbreak Alert                                                                       |
| Outbreak Alert Time Frame Analysis                                                  | Identify and deactivate outbreak alerts whose investigation time frame has expired.                                                             |
| Remediate and Mitigate Outbreak Response Alert                                      | Block all types of outbreak response alert indicators on the firewall according to their block status and take steps to mitigate them.          |
| Reset Outbreak to Tracking                                                          | Set the deactivated and resolved outbreak alert to tracking                                                                                     |
| Stop Outbreak Alert Record Tracking                                                 | Update the status of the outbreak alert to "Resolved," and include the resolved notes and resolved reason in the associated outbreak alert.     |
| Tracking Outbreak: Retrieve CVEs and IOCs                                           | Fetch outbreak alert CVEs (KVE) from NIST and IOCs from Fortinet FortiGuard, specifically focusing on those marked with a status of 'Tracking'. |
| Update CVE Details from NIST ![new](./res/icon-new.svg)                             | Fetches CVE Details from NIST and Updates the CVE record                                                                                        |
| Update Outbreak Alert Details ![new](./res/icon-new.svg)                            | Fetches and Updates the Outbreak Alert's Details                                                                                                |

| 05 - Hunt |
|:---------:|

| Playbook Name                                                                   | Description                                                                                                                          |
|:--------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| IOC Hunting                                                                     | Investigate the IOCs of the Outbreak Alert using threat-hunting tools.                                                               |
| IOC Hunting – FortiSIEM                                                         | Perform IOC hunting using Fortinet FortiSIEM with the specified list of IOCs.                                                        |
| IOC Hunting - FortiSIEM > Fetch Incident Associated Events                      | Retrieve associated events for the incident from Fortinet FortiSIEM.                                                                 |
| IOC Hunting - FortiAnalyzer                                                     | Performs IOC hunting using Fortinet FortiAnalyzer with the specified list of IOCs.                                                   |
| IOC Hunting - FortiAnalyzer > Device Log Search                                 | Hunt IOCs using bulk device log search and create the Incident.                                                                      |
| IOC Hunting - Splunk                                                            | Performs IOC hunting using Splunk with the specified list of IOCs.                                                                   |
| IOC Hunting - IBM QRadar                                                        | Performs IOC hunting using IBM QRadar with the specified list of IOCs.                                                               |
| Threat Hunting (Fortinet Fabric) - FortiSIEM                                    | Retrieves an incident from the Fortinet FortiSIEM server based on the outbreak alert event type.                                     |
| Threat Hunting (Fortinet Fabric) - FortiSIEM > Fetch Incident                   | Retrieve incident details for the specified outbreak alert from Fortinet FortiAnalyzer and create an incident in Fortinet FortiSOAR. |
| Threat Hunting (Fortinet Fabric) - FortiSIEM > Create Incident                  | Create incidents in Fortinet FortiSOAR using the outbreak incidents retrieved from Fortinet FortiSIEM.                               |
| Threat Hunting (Fortinet Fabric) - FortiSIEM > Fetch Associated Incident Events | Retrieve all associated events for a specified outbreak incident from Fortinet FortiSIEM using the incident ID.                      |
| Threat Hunting (Fortinet Fabric) - FortiAnalyzer                                | Retrieve all events from Fortinet FortiAnalyzer using the outbreak alert filter query.                                               |
| Threat Hunting (Fortinet Fabric) - FortiAnalyzer > Get Related Event Assets     | Retrieve event logs and device details from Fortinet FortiAnalyzer based on the outbreak events.                                     |
| Threat Hunting (Signature Based) - Splunk                                       | Invokes a search on the Splunk server based on the outbreak alert search query.                                                      |
| Threat Hunting (Signature Based) - Splunk > Create Inbound Incident             | Creates an Incident in Fortinet FortiSOAR using the event data found for the associated outbreak.                                    |
| Threat Hunting (Signature Based) - Splunk > Update Notable Fields               | Invokes a search on the Splunk server based on the outbreak notable data.                                                            |
| Threat Hunting (Signature Based) - IBM QRadar                                   | Executes an outbreak alert Ariel query on the IBM QRadar server and create FortiSOAR Incident.                                       |
| Threat Hunting (Signature Based) - Get Events - FortiSIEM                       | Retrieves a list and details of events from the Fortinet FortiSIEM server based on the outbreak alert signature query.               |
| Threat Hunting (Signature Based) - Get Events - FortiAnalyzer                   | Retrieves a list and details of incidents from the Fortinet FortiAnalyzer server based on the outbreak alert event type.             |
| Threat Hunting (Signature Based)  - FortiAnalyzer > Log Search                  | Retrieves a logs from the Fortinet FortiAnalyzer server based on the outbreak alert signature query.                                 |

>[!Warning]
>We recommend that you clone these playbooks before customizing to avoid loss of information while upgrading the solution pack.

## System View

| Name                | Description                               |
|:--------------------|-------------------------------------------|
| Outbreak Management | Displays details of the selected outbreak |

## Schedules

| Name                                                                  | Description                                                                                                                             |
|:----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| `Investigate_Outbreak-Alerts`                                         | Automatically identifies new and ongoing outbreak alerts and forwards them for thorough investigation using advanced threat-hunting tools. |
| `Outbreak_Alert-Time-Frame-Analysis`                                  | Efficiently identifies and deactivates outdated outbreak alerts based on their investigation time frame.                                   |
| `Outbreak_Automated-Deployment-Outbreak-Alert-Response-Solution-Pack` | Seamlessly installs the latest outbreak alert solution packs (from the past X days) with automated email notifications.                  |
| `Outbreak_Ingest-Tracking-Outbreak-CVEs-and-IOCs`                     | Retrieve outbreak alert CVEs (KVE) from NIST and IOCs from Fortinet FortiGuard, focusing on those marked as `Tracking`.                 |
| `Outbreak_Alert_Fetch_Latest_Details`                                 | Fetches and Updates the Outbreak Alerts with the latest details.                                                                        |

# Next Steps

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) |
|-----------------------------------------|-------------------------------------------|---------------------|
