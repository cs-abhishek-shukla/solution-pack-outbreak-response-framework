| [Home](../README.md) |
| -------------------- |

# Overview: Outbreak Response Framework

The **Outbreak Response Framework** provides real-time alerts and actionable intelligence regarding active cybersecurity threats. Designed to help organizations respond swiftly to emerging threats, this framework leverages data from FortiGuard's Outbreak Detection Service and integrates seamlessly with FortiSOAR&trade;.

## Outbreak Alerts

Outbreak alerts, disseminated through the FortiGuard service, provide comprehensive information about newly identified cyber threats. These alerts typically contain details such as the nature of the threat (e.g., malware, ransomware, phishing), the affected systems or applications, and recommended mitigation strategies. Additionally, the alerts may include specifics on the threat's propagation methods, exploited vulnerabilities, and Indicators of Compromise (IoCs), which help in identifying the presence of a threat within a network.

The **Outbreak Response Framework** solution pack processes these alerts and compiles critical data, including:

- **Attack Narrative**: A detailed description of the attack, including its timeline and the technologies affected. The narrative includes:
  - **Description**: An in-depth analysis of the vulnerability being exploited.
  - **Background**: Contextual information explaining the factors contributing to the vulnerability.
  - **Announcement**: Early warnings about zero-day vulnerabilities.
  - **Latest Developments**: Updates on mitigation measures.
  - **CVE List**: A compilation of CVEs (Common Vulnerabilities and Exposures) relevant to the threat, serving as a reference for publicly known security issues .

- **Indicators of Compromise (IoCs)**: A list of known IoCs associated with the outbreak, aiding in the detection and identification of the threat within affected systems .

## Threat Hunt Rules

The **Outbreak Response Framework** solution pack employs a set of Threat Hunt Rules to investigate and respond to outbreak alerts. Each outbreak alert is linked to three primary types of Threat Hunt Rules:

1. **Fortinet Fabric Rules**:
    - **FortiAnalyzer**: FortiAnalyzer is a centralized logging and reporting appliance that collects, analyzes, and reports on security events and logs from various Fortinet security devices. It is instrumental in managing outbreaks by providing centralized logging, real-time monitoring, and threat detection, among other features .
    - **FortiSIEM**: FortiSIEM offers comprehensive security information and event management capabilities. It enhances outbreak response by aggregating logs, performing real-time monitoring, conducting behavioral analysis, and integrating threat intelligence .

2. **Sigma Rules**: Sigma rules are platform-agnostic and enable consistent threat detection across different security platforms. These rules facilitate rapid development and deployment, community collaboration, granular threat detection, and adaptability to new threats .

3. **YARA Rules**: YARA is a rule-based pattern-matching language designed for identifying and classifying malware. YARA rules are highly flexible and customizable, allowing for precise detection of specific threat attributes. These rules are scalable, incorporate IoCs, and benefit from community collaboration, enhancing their effectiveness in outbreak detection .

The **Outbreak Response Framework** within FortiSOAR provides organizations with the tools and intelligence needed to effectively respond to cybersecurity outbreaks, ensuring a robust and proactive defense posture.

# Next Steps

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Usage](./usage.md) |
|-----------------------------------------|-------------------------------------------|---------------------|
