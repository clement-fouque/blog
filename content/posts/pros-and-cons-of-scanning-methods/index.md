---
title: "Pros and Cons of vulnerability scanning methods"
date: 2023-07-20T12:29:57Z
draft: true
---

Choosing scanning methods is critical in the success of a vulnerability management program. Each method has its own advantages and disadvanatges. One might better suits in one environment and not in another. 

I'll go through each scanning method by defining the pros and cons. Then I'll provide my recommendation in regards to specificities of environments. 

## Types of scanning methods
### Unauthenticated scans
An unthenticated scan is launch from the vulnerability scanner and is going through a list of IPs or asset names, one after the other. As it doesn't have access to the asset, it can scan different type of assets (network, servers, workstations, ...).

#### Pros
<mark>Fairly easy to implement</mark><br/>
It's the easiest and quickest scanning method to implement. We don't need to know the environment well to configure the scan and launch it. We just have to configure the ip range(s) and or domain(s). 

<mark>Best for asset discovery</mark><br/>
As it doesn't have prerequisites, it's excellent to discover unknown assets on the network. 

<mark>Excellent for external attack surface management</mark><br/>


#### Cons
<mark>Network access</mark><br/>
As the scan is launched from the vulnerability scanner, you need to manage the network connections between the scanner and assets. In enterprise segmented networks, it's a challenge to maintain this. 

### Authenticated scans

There might some scanners that will perform unauthenticated scan if authentication is failing. 

### Agent-based scans

### Agentless scans (cloud only)

## Pros and cons
| Scan method | Pros | Cons |
|--|--|--|
| Unauthenticated scan | - Fairly easy to implement<br/>- View of an external actor<br/>- Excellent coverage | - Limited results |
| Authenticated scan | <br/>- View of an external actor<br/>- Excellent coverage | - Credential and network management |

## References

