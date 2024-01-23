---
title: "Exploring vulnerability scanning methods: pros and cons"
date: 2023-07-20T12:29:57Z
draft: true
---

Choosing the right scanning methods is critical for the success of a vulnerability management program. Each method has its own advantages and disadvantages, and some might be better suited to one environment/context than another. These scanning methods are not mutually exclusive. 

Let's delve into each scanning method, defining the pros and cons for better understanding, and then provide recommendations based on specific environment requirements.

## Types of scanning methods
### Unauthenticated scans
An unauthenticated scan involves probing and testing a system or application without using any login credentials or authentication.

#### Pros

| Title | Details |
|--|--|
| Easy setup | Unauthenticated scans are quick to set up as they don't require any login information or special permissions. |
| Comprehensive Coverage | Network-based scanning provides an overview of all devices connected to the network, ensuring no potential entry points are overlooked. It's excellent for scanning the external perimeter as we often have limited/reduced knowlege of the whole perimeter.
| External perspective | Unauthenticated scans mimic the approach of potential attackers, providing insight into the vulnerabilities visible from the outside. |

#### Cons
| Title | Details |
|--|--|
| Limited visibility | Without proper credentials, the scan may miss some internal vulnerabilities and misreport certain findings. |
| Performance impact | Depending on the scanner's settings, authenticated scans might have a significant impact on the systems due to increased activity during the scan. |
| Accuracy | Factors like network conditions and asset availability can affect the scan results, leading to varying outcomes even for identical scans (e.g Workstations are often turned off outside working hours)|
| Troubleshooting | The lack of precise scheduling in authenticated scans can complicate troubleshooting efforts, as it requires going through scan logs to identify when an asset was scanned. |

### Authenticated scans
An authenticated scan involves using valid credentials to access the target system or application, allowing the scanner to perform a more comprehensive assessment.

#### Pros
| Title | Details |
|--|--|
| Fairly easy setup |  |
| Detailed Results | Authenticated scans can provide more detailed information about vulnerabilities within the system, including configuration issues and software-specific weaknesses. |
| No agent installed | IT teams are often reluctant to install an agent on their systems, making authenticated scans a common option.

#### Cons
| Title | Details |
|--|--|
| Credential management | Managing and storing credentials securely can be challenging, as they provide significant access to the target systems. |
| Performance impact | Similar to unauthenticated scans, authenticated scans might have a significant impact on the systems due to increased activity during the scan. |
| Accuracy | Factors like network conditions and asset availability can affect the scan results, leading to varying outcomes even for identical scans (e.g Workstations are often turned off outside working hours)|
| Troubleshooting | The lack of precise scheduling in authenticated scans can complicate troubleshooting efforts, as it requires going through scan logs to identify when an asset was scanned. |

### Agent-based scans
Agent-based scanning involves installing a specialized software agent on each target system that continuously monitors and reports vulnerabilities to a centralized management console.

#### Pros
| Title | Details |
|--|--|
| Real-Time monitoring | Agent-based scans offer real-time monitoring and continuous assessment of vulnerabilities, providing immediate alerts for new threats. |
| Troubleshooting| Agent-based scans can simplify troubleshooting efforts by providing real-time data directly from the agents. |
| Easy architecture | Managing outbound connections (from the asset to the scanner console) is often easier than handling inbound connections, simplifying network setup.
| Scan duration | All agents can simultaneously scan, reducing the overall scan duration.
| No rescan needed | Agents continuously monitor, eliminating the need for frequent rescanning.|
| Performance impact | Agent are lightweigth and the extension of the scan duration to limit the load will not impact the overall scan duration| 

#### Cons
| Title | Details |
|--|--|
| Deployment Overhead | Installing and maintaining agents on each system can be time-consuming and resource-intensive, especially in large-scale environments. | 
| Agent Compatibility | Ensuring agent compatibility with various operating systems and applications can be challenging, potentially leading to limitations in coverage. | 
| | Adds additional software components to the environment, which could introduce vulnerabilities or performance issues. 

### Agentless scans
Agentless scanning involves conducting vulnerability assessments without installing any additional software on the target systems. Instead, it relies on existing protocols and network communication to gather information.

#### Pros
| Title | Details |
|--|--|
| Easy deployment | Agentless scans are easy to deploy since they do not require any installation on the target systems. |
| Lower resource usage | Without agents, there is no ongoing overhead on system resources, reducing the impact on performance. |
| Reduced security risks | Since there are no additional agents, potential vulnerabilities associated with them are eliminated. |

#### Cons
| Title | Details |
|--|--|
| Cloud only | Available in the cloud only and usually only on the main ones (AWS, Azure, and GCP). |
| Architecture | Depending on the solution, it could be quite complex to configure a scanner per region. |
| Cost in large environment | The cost of a snapshot to perform the scan and the network transfer fees might explode costs. |
| Limited Visibility | Agentless scans may lack some of the deeper insights into vulnerabilities that can be obtained through agent-based scans. |

## Other considerations
- False positive: unauthenticted scans are more prone to false-positive. However, it's highly dependant on the vulnerability scanner.
- Scan duration: A network scan is scanning assets in sequential mode. Concurrency can be increase to reduce the time with the risk of performing a denial of service on the asset. The scan will be complete when all assets will be scanned. For an agent-based scan, all agents can scan at the time and report vulnerabilities to the scanner. The duration is reduced with agent-based scans.
- Architecture: depending on 
- Costs
- Why is the performance better with an agent rather than with network scans ?

## Pros and cons
| Scan method | Pros | Cons | Best for
|--|--|--|--|
| Unauthenticated scan | - Fairly easy to implement<br/>- View of an external actor<br/>- Excellent coverage | - Limited results | - External attack surface management
| Authenticated scan | <br/>- View of an external actor<br/>- Excellent coverage | - Credential and network management | - Where you can't install an agent


## References
- https://www.aquasec.com/cloud-native-academy/cspm/agentless-vs-agent-based-security/
- https://learn.microsoft.com/en-us/azure/defender-for-cloud/concept-agentless-data-collection

Happy scanning!