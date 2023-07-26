---
title: "Pros and Cons of vulnerability scanning methods"
date: 2023-07-20T12:29:57Z
draft: true
---

Choosing the right scanning methods is critical in the success of a vulnerability management program. Each method has its own advantages and disadvanatges. One might better suits in one environment/context and not in another. Those scanning methods are not mutually exclusive. 

I'll go through each scanning method by defining the pros and cons. Then I'll provide my recommendation in regards to environments specificities. 

## Types of scanning methods
### Unauthenticated scans
An unthenticated scan is launch from the vulnerability scanner and is going through a list of IPs or asset names, one after the other (there might be concurrency). It can scan different type of assets (network, servers, workstations, ...).

#### Pros
| Title | Details |
|--|--|
| Fairly easy to implement | It's the easiest and quickest scanning method to implement a scan. We don't need to know the environment well to configure and launch it. We just have to configure the ip range(s) and or domain(s) and we are ready to go. 
| Best for asset discovery | As it doesn't have prerequisites such as account access or a software installed, it's excellent to discover assets on the network. It's excellent for scanning the external surface as we often have limited/reduced knowlege of the whole perimeter.
| View of an external actor | Due to its nature, we can get the same information as an attacker would have. Findings from an unauthenticated scan should increase the priority of the remediations |

#### Cons
| Title | Details |
|--|--|
| Network access | As the scan is launched from the vulnerability scanner, you need to manage the network connections between the scanner and assets. In enterprise segmented networks, it's a challenge to maintain this. | 
| Limited findings and contextual data | As the scanner doesn't have full access to the asset, it'll only detect vulnerabilities that can be discovered externally. A lot of vulnerabilities will be missed. We'll not be able to add contextual data to the asset. |
  Accuracy | Many factors (e.g. network, availability, ...) are affecting the scan results. Two identical scans might come with different results |


### Authenticated scans

> There might some scanners that will perform unauthenticated scan if authentication is failing. 

#### Pros
| Title | Details |
|--|--|
| Full visibility on the asset | As the account used for the scanning has full access on the asset, it'll be able to identify vulnerabilities locally and retrieve contextual data. 
| No agent installed | IT teams are often reluctant to install an agent on their systems. They're more willing to provide an account

#### Cons
| Title | Details |
|--|--|
| Network and credential management | The scanner will need to have access to all assets of the networks. In some environments, it could a big challenge. If we had the service accounts credential management, it could become a nightmare. If the scanner doesn't have access to the asset, there'll be no findings. |
| Asset's availability | The asset needs to be up and running at the time the scan is occurring. For asset type like workstations, it's challenge as people usually turn off their endpoint at the end of the day. It's impossible to know if the asset is down or if there was a connection issue. |
| Troubleshooting | When there are performance issues, the first thing that is checked is if a scan was running. As the scheduling is not really precised, it makes troubleshooting harder as we have to go through the scan logs to see if and when an asset was scanned. |
| Accuracy | | 

### Agent-based scans
An agent is installed on every asset and the configuration is managed from a centralized console. The agent is scanning the asset at specific intervals (every 4 hours, daily, ...) and is pushing the results to the console.

#### Pros
| Title | Details |
|--|--|
| Accuracy | We know that at each interval the scan is launched, we'll have the latest data. If there is no data, it means the asset is unavailable or the service is stopped/crashed.
| Troubleshooting|  |
| Network access | We only have to manage the outbound connection (from the asset to the scanner console). It usually has less constraints than inbound connections. 

#### Cons
| Title | Details |
|--|--|
| Accuracy | | 
| Troubleshooting | |

### Agentless scans (cloud only)

#### Pros
| Title | Details |
|--|--|
| Deployment's speed | |
| Troubleshooting | |

#### Cons
| Title | Details |
|--|--|
| Cloud only | |
| Architecture | |

## Pros and cons
| Scan method | Pros | Cons | Best for
|--|--|--|--|
| Unauthenticated scan | - Fairly easy to implement<br/>- View of an external actor<br/>- Excellent coverage | - Limited results | - External attack surface management
| Authenticated scan | <br/>- View of an external actor<br/>- Excellent coverage | - Credential and network management | - Where you can't install an agent


## References

