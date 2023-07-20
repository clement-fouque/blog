---
title: "Pros and Cons of vulnerability scanning methods"
date: 2023-07-20T12:29:57Z
draft: true
---

Choosing scanning methods is critical in the success of a vulnerability management program. Each method has its own interest and one might suits better in one environment and not in another one. 

I'll go through each scanning method by defining the pros and cons. Then I'll provide my recommendation in regards to specificities of environments. 

## Types of scanning methods
### Unauthenticated scans
#### Pros
<mark>Fairly easy to implement</mark><br/>
It's the easiest and quickest to implement. We don't need to know the environment well to configure the scan and launch it. We just have to configure the ip range(s) and or domain(s).

<mark>Fairly easy to implement</mark><br/>
It's the easiest and quickest to implement. We don't need to know the environment well to configure the scan and launch it. We just have to configure the ip range(s) and or domain(s).


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

