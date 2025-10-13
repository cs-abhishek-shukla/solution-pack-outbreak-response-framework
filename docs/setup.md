|[Home](../README.md) |
|--------------------------------------------|

# Installation

1. To install a solution pack, click **Content Hub** > **Discover**.
2. From the list of solution packs that appear, search **Outbreak Response Framework**.
3. Click the **Outbreak Response Framework** solution pack card.
4. Click **Install** on the lower part of the screen to begin the installation.

## Prerequisites

The **Outbreak Response Framework** solution pack depends on the following solution packs. These solution packs are installed automatically &ndash; if not already installed.

| Name                     | Type          | Version           | Purpose                                |
|:-------------------------|:--------------|:------------------|:---------------------------------------|
| SOAR Framework           | Solution Pack | v3.3.0 and later  | Required for Incident Response modules |
| Threat Intel Management  | Solution Pack | v3.0.0  and later | Required to ingest threat feeds        |
| Vulnerability Management | Solution Pack | v2.2.0  and later | Required to ingest CVEs for KEVs       |

# Configuration

## Install and Configure Connectors

For the **Outbreak Response Framework** solution pack, install and configure the following connectors:

- **NIST National Vulnerability Database** - The NIST National Vulnerability Database (NVD) is the U.S. government repository of standards-based vulnerability management data represented using the Security Content Automation Protocol (SCAP). This data enables automation of vulnerability management, security measurement, and compliance. The NVD includes databases of security checklist references, security-related software flaws, misconfigurations, product names, and impact metrics. To configure and use the NIST National Vulnerability Database connector, refer to [Configuring NIST National Vulnerability Database](https://docs.fortinet.com/fortisoar/connectors/nist-nvd)

- Any, or all, of the following hunt tools:

    - **Fortinet FortiAnalyzer** - FortiAnalyzer is the NOC-SOC security analysis tool built with an operations perspective. FortiAnalyzer (FAZ) supports analytics-powered use cases to provide better detection against breaches. To configure and use the Fortinet FortiAnalyzer connector, refer to [Configuring Fortinet FortiAnalyzer](https://docs.fortinet.com/fortisoar/connectors/fortianalyzer)

    - **Fortinet FortiSIEM** - Fortinet FortiSIEM is a highly scalable multi-tenant Security Information and Event Management (SIEM) solution that provides real-time infrastructure and user awareness for accurate threat detection, analysis, and reporting. To configure and use the Fortinet FortiSIEM connector, refer to [Configuring Fortinet FortiSIEM](https://docs.fortinet.com/fortisoar/connectors/fortisiem)

    - **IBM QRadar** - IBM QRadar SIEM helps your business by detecting anomalies, uncovering advanced threats, and removing false positives. It consolidates log events and network flow data from thousands of devices, endpoints, and applications distributed throughout a network. To configure and use the IBM QRadar connector, refer to [Configuring IBM QRadar](https://docs.fortinet.com/fortisoar/connectors/ibm_qradar)

    - **Splunk** - Splunk connector allows users to invoke search, fetch events to related search, invoke alert actions, update notables, sync Splunk users to FortiSOAR, etc. To configure and use the Splunk connector, refer to [Configuring Splunk](https://docs.fortinet.com/fortisoar/connectors/splunk_new)

## Setting up Outbreak Response Framework on FortiSOAR

After installation of the **Outbreak Response Framework** solution pack, run the configuration wizard to ready your FortiSOAR environment to investigate *Outbreak Alerts*. This wizard helps you select and configure **Threat Hunting Integrations** on FortiSOAR.

> [!Important]
> After an upgrade run the **Outbreak Response Framework** configuration wizard again.

You can launch the Outbreak Response Framework configuration wizard by any of the following methods:

1. **From navigation menu**
    - Navigate to **Outbreak Management** > **Outbreak Alerts**, if running the wizard for the first time.

        ![Outbreak Response configuration start page](./res/config-wizard-00-b.png)

2. **From Content Hub**
    1. Navigate to **Resources** > **Content Hub**
    2. Search for **Outbreak Response Framework**
    3. Click the *Outbreak Response Framework* card
    4. Click the button **Configure** from the lower-left of the screen.

        ![Outbreak Response start configuration](./res/config-wizard-00.png)        

> [!NOTE]
> The configuration wizard can be **re-launched** only from *Content Hub*.

### Launching the Outbreak Response Framework Configuration Wizard

Click the button **Setup Outbreak Response Framework** on the Outbreak Response Framework configuration page.

![Outbreak Alert get started](./res/config-wizard-01.png)

### Selecting Threat Hunting Integrations
    
Select *Threat Hunting Integrations* to run outbreak response hunt activities and click **Next**.

The hunt activities require searching for adversaries and their tactics, within an environment, against existing information available in the Threat Intel Platform's database (TIP). The *Threat Hunting Integrations* help run the threat hunt activities and are an important part of the *Outbreak Response Framework*.

![Select Integrations page](./res/config-wizard-02.png)

### Configuring Integrations

Select each integration's tab to configure the associated connector and data ingestion parameters. The page has separate tabs for each integration selected as a threat detection source:

- **Configure the NIST NVD connector**: Refer to [NIST NVD](https://docs.fortinet.com/fortisoar/connectors/nist-nvd) connector documentation for more information.

    ![Configure NIST Integration page](./res/config-wizard-03-nist.png)

- **Configure the Fortinet FortiAnalyzer**: Refer to [Fortinet FortiAnalyzer](https://docs.fortinet.com/fortisoar/connectors/fortianalyzer) connector documentation for more information.

    You can also configure the Fortinet FortiAnalyzer connector on agent. To run FortiAnalyzer connector actions using an agent, you need the following:

    - **A virtual machine (VM) in the FortiAnalyzer network**: Refer to [recommended specifications](https://docs.fortinet.com/document/fortisoar/7.6.2/deployment-guide/158469/deploying-fortisoar#Recommended_specifications_for_FSR_agents) and [Prerequisites](https://docs.fortinet.com/document/fortisoar/7.6.2/deployment-guide/158469/deploying-fortisoar#Prerequisites_for_installing_an_FSR_agent) for installing an agent sections in FortiSOAR product document.

    - **Adding the agent**: Refer to [Adding an agent](https://docs.fortinet.com/document/fortisoar/7.6.2/deployment-guide/158469/deploying-fortisoar#Adding_an_FSR_agent) on FortiSOAR product documentation.

    - **Installing agent on the VM**: Refer to [Installing an Agent](https://docs.fortinet.com/document/fortisoar/7.6.2/deployment-guide/158469/deploying-fortisoar#Installing_an_FSR_Agent) on FortiSOAR product documentation.

    - **Installing the Fortinet FortiAnalyzer connector on Agent**: Refer to [Installing a connector on an FSR agent](https://docs.fortinet.com/document/fortisoar/7.6.2/administration-guide/204303/segmented-network-support#Installing_a_connector_on_an_FSR_agent) on FortiSOAR product documentation.
    
    If the agent is installed and configured, it appears under the Select Configuration drop-down.

    ![Configure Fortinet FortiAnalyzer Integration page](./res/config-wizard-03-faz-1.png)

    Select the default target and configuration to use when Outbreak Management executes the Fortinet FortiAnalyzer connector's actions.

    ![Specify Fortinet FortiAnalyzer configuration to use](./res/config-wizard-03-faz-2.png)

### Investigation Schedule

![Investigation Schedule page](./res/config-wizard-04.png)

- **Threat Hunt Window**: Specify the number of days as an interval within which outbreak should be considered for investigation.

- **Investigation Frequency**:  Select the frequency of the investigation to create a schedule. The created schedule can be found under *Automation* > *Schedules*. Once created, the schedule periodically runs the investigation on the reported outbreaks at the specified frequency.

### Installation & Notification

![Installation and notification page](./res/config-wizard-05.png)

- **Auto Installation Criteria**: Select one of the following options:
    - **Install Selected Outbreak Response Solution Packs**:  
Select the severity, and the last `X` days, of the outbreak to install the corresponding solution pack. You can select one or more severity from the following options:
        - *Critical*
        - *High*
        - *Medium*
    - **Install All Outbreak Response Solution Packs**: Select to install all outbreak response solution packs. 

- **Outbreak Alert Update Notification**:  Specify email addresses authorized to receive outbreak updates. You can specify multiple email addresses separated by a comma.

### Summary

Click the button **Ingest Now** to install the outbreak-specific response solution packs of the severity selected on the previous screen.

Click **Finish** to complete the configuration process.

![All set](./res/config-wizard-06.png)

# Next Steps

| [Usage](./usage.md) | [Contents](./contents.md) |
|---------------------|---------------------------|
