---
layout: post
title: "AV vs Sandbox"
description: "A comparative discussion between traditional Anti-Virus technologies that perform scan/compare vs Malware control that is based upon Sand boxing"
tags: mck
categories: mck
---

# Anti-Virus vs. Sandbox Technology

## Anti-Virus vs. Sandbox Technology

AntiVirus (AV) software operates based on the idea that you can decide what is bad, detect which programs do bad things, and kill/uninstall them. Reactive security systems like AV software require very good knowledge about the threats you're facing, or about the difference between malicious and normal behaviour. That makes them costly and imprecise.

Sandboxes operate on the idea that you cannot decide what is good or bad, but the user can decide what they choose to trust. They provide you with the ability to confine or isolate specific programs so that if they do bad things, it doesn't do any harm to things outside the sandbox. The downside of confinement systems is that there must be a logical and simple way for the system or for its users of deciding which programs get confined where, and which are also to talk to each other.

A sandbox is basically a context in which a piece of software can be run isolated from the rest of the world. Java applets running in a browser is a classic example, as should be Flash (though it is apparently not nearly as well isolated and safe as would be ideal): These are contexts where programs can run without having access to resources on the host machine (your PC), such as your file system, etc.

## SentinelOne (S1) Endpoint Protection Platform

SentinelOne Endpoint Protection Platform provides a multi-layered approach for detecting malware, exploit and script-based attacks using a combination of machine learning coupled with both static analysis and system-wide behaviour monitoring to isolate and mitigate threats in real time. The management system, which can be deployed either in the cloud or on-premise, provides forensic analysis of threats and allows administrators to quickly resolve attacks through automated remediation and rollback features.

SentinelOne uses Dynamic Behavioral Tracking, that runs realtime, on the endpoint and utilizes advanced machine learning to detect behavioral patterns as application and code is executing on the device. Done across Windows, Mac and Linux with their own proprietary, patent pending technology. Works on devices even completely OFFLINE, and is an autonomous module, that can detect, mitigate and remediate threats in real time. No connection to the cloud needed, no hashes, no signatures.

SentinelOne has “Cloud Intelligence”, which is in essence a way of crowdsourcing information between all of the intelligence gathered, either from their client base (if they opt-in), and/or from third party reputation feeds, VT included. It is NOT part of their detection engine, and its entire purpose is to validate hashes, out of band, regardless of our Dynamic Behavioral Tracking engine.

SentinelOne is NOT a scan engine. It doesn't scan files or check for signatures. It monitors code execution on a live system – VERY different than a scan engine.

### SentinelOne (S1) Specifics

**High-Level Features**

- Learning mode – establishes a baseline of legitimate applications running on endpoints to minimize false positives.
- Cloud intelligence – proactively blocks known threats by leveraging cloud intelligence and select reputation services.
- Auto immune – instantly shares new threat intelligence across endpoints to prevent lateral movement and further infection.
- Anti-exploitation detect and prevent application and memory-based exploits based on the techniques themselves without relying on static measures.
- Dynamic execution inspection – continuously monitors and tracks activity on endpoints to analyze behavior and detect unknown threats.
- Automated mitigation – fully automates remediation and threat removal, including killing processes, and quarantining threats or endpoints.
- Remediation – recovers deleted files or restores modified files back to their state prior to malware execution, effectively reversing any malware-driven modifications. <--- can restore files encrypted by ransomware.
- Endpoint forensics – graphical reports generated during attacks deliver sandbox equivalent investigative capabilities.

**Details**

- Blocks known in-the-wild threats by leveraging up to the minute cloud intelligence and select reputation services to proactively block threats before they can execute on endpoints.  Think Wild Fire - solution that uses Threat Intelligence data from various sources to provide more update to date reputation to IP address and files.

- Prevents attacks that use memory and application exploits by detecting their execution techniques (e.g., heap spraying, stack pivots, ROP attacks, and memory permission modifications.  Provides kernel level protection to prevent privilege escalation via exploits.

- Stops targeted and zero day attacks using real-time execution monitoring and analysis to assemble true behavioral context without the need for static measures. SentinelOne performs monitoring and analysis of application and process behaviors at low-level instrumentation of OS activities and operations, including memory, disk, registry and network

- Beyond just detection, manual or fully automated mitigation options can be configured via policy and include various actions such as: killing malicious processes, quarantining threats or isolating infected machines.

### SentinelOne (S1) Performance 
 
- CPU = 2%
- Memory = 300mb of ram
- Footprint = 800mb of storage (assuming full logs are enabled)

### SentinelOne (S1) Guarantee

SentinelOne also is offering to pay a victim's ransom if its endpoint security product should fail to block the initial infection or effect-related remediation.

[Protection Against Ransomware Guaranteed](https://sentinelone.com/wp-content/uploads/2016/07/Brochure-Ransomware-Vertical-Online.pdf)

SentinelOne's program offers to reimburse customers up to $1,000 per infected endpoint, or up to $1 million in total. But there are many conditions, and the guarantee isn't free.

Clients will pay a surcharge of between 5 to 10 percent of the per-seat cost of their SentinelOne license, which varies according to the vagaries of software license subscription negotiations.

The SentinelOne guarantee is also contingent on customers configuring their software and computers in certain ways. For example, organizations must have Windows Volume Shadow Copy Service enabled, which allows machines to be rolled back and restored.

### SentinelOne (S1) Costing

- about $45 per endpoint @3500 endpoints per year

### SentinelOne (S1) Review vs. Cylance

I have heavily reviewed Cylance and SentinelOne; I preferred SentinelOne for their builtin, one button or automatic, isolation and remediation along with their visual kill chain capability.

Also with the recent RIFFS ands news about fake testing; unknown about the future; also they are actually more expensive.

Currently ISRM is performing a bake-up; which includes  SentinelOne (S1), but their requirements are greatly differ.  They are looking for malware and forensics; which is really wide and no single product will provide that coverage.  They are looking at 2 other platforms that focus more on the forensic side.


# Executive Summary

## Current Solution

EIS is currently using McAfee Endpoint Security Threat Prevention for Malware control using McAfee ePO in the Cloud.  The decision to go with this direction was based upon leveraging ISRM licensing model (all-you-can-eat free of charge) utilization the option of management in cloud to minimize CAPEX cost for servers and licensing and to minimize operations impact.

The solution was deployed per McAfee's and Microsoft "best practices" to minimize application/system impact.  Additional consideration was included for application SME to further ensure minimal risk to the application(s).  

## Current Challenges

 McAfee Endpoint Security Threat Prevention solution has been severely impacting production systems/applications. EIS has actively worked with McAfee - following their processes - performing updates without any resolution.

- High CPU and memory usage on multiple servers due to McAfee services
- Exclusion policies are not getting applied to the servers due to character limitation with ENS 10.5.0
- ENS 10.5.x is not compatible with single core CPU, there are 184 servers managed by EIS with single CPU, cannot upgrade AV module to latest version.
-  Recommendations from McAfee's engineers for most of the reported issues were to wait and upgrade to next version which is not acceptable.
-  

## Go Forward Strategy

The current strategy is to move away from traditional anti-malware/anti-virus deployments i.e scan engines and move forward into sandbox based solutions.

AntiVirus (AV) software operates based on the idea that you can decide what is bad, detect which programs do bad things, and kill/uninstall them. Reactive security systems like AV software require very good knowledge about the threats you're facing, or about the difference between malicious and normal behaviour. That makes them costly and imprecise.

Sandboxes operate on the idea that you cannot decide what is good or bad, but the user can decide what they choose to trust. They provide you with the ability to confine or isolate specific programs so that if they do bad things, it doesn't do any harm to things outside the sandbox. The downside of confinement systems is that there must be a logical and simple way for the system or for its users of deciding which programs get confined where, and which are also to talk to each other.

A sandbox is basically a context in which a piece of software can be run isolated from the rest of the world. Java applets running in a browser is a classic example, as should be Flash (though it is apparently not nearly as well isolated and safe as would be ideal): These are contexts where programs can run without having access to resources on the host machine (your PC), such as your file system, etc.

### Vendor Choice

We will reviewing SentinelOne Endpoint Protection Platform as our primary choice as this aligns with our current needs and with the current evaluation ISRM is performing.  

SentinelOne Endpoint Protection Platform provides a multi-layered approach for detecting malware, exploit and script-based attacks using a combination of machine learning coupled with both static analysis and system-wide behaviour monitoring to isolate and mitigate threats in real time. The management system, which can be deployed either in the cloud or on-premise, provides forensic analysis of threats and allows administrators to quickly resolve attacks through automated remediation and rollback features.

SentinelOne uses Dynamic Behavioral Tracking, that runs realtime, on the endpoint and utilizes advanced machine learning to detect behavioral patterns as application and code is executing on the device. Done across Windows, Mac and Linux with their own proprietary, patent pending technology. Works on devices even completely OFFLINE, and is an autonomous module, that can detect, mitigate and remediate threats in real time. No connection to the cloud needed, no hashes, no signatures.

SentinelOne has “Cloud Intelligence”, which is in essence a way of crowdsourcing information between all of the intelligence gathered, either from their client base (if they opt-in), and/or from third party reputation feeds, VT included. It is NOT part of their detection engine, and its entire purpose is to validate hashes, out of band, regardless of our Dynamic Behavioral Tracking engine.

SentinelOne is NOT a scan engine. It doesn't scan files or check for signatures. It monitors code execution on a live system – VERY different than a scan engine.

### Benefits

**High-Level Features**

- Learning mode – establishes a baseline of legitimate applications running on endpoints to minimize false positives.
- Cloud intelligence – proactively blocks known threats by leveraging cloud intelligence and select reputation services.
- Auto immune – instantly shares new threat intelligence across endpoints to prevent lateral movement and further infection.
- Anti-exploitation detect and prevent application and memory-based exploits based on the techniques themselves without relying on static measures.
- Dynamic execution inspection – continuously monitors and tracks activity on endpoints to analyze behavior and detect unknown threats.
- Automated mitigation – fully automates remediation and threat removal, including killing processes, and quarantining threats or endpoints.
- Remediation – recovers deleted files or restores modified files back to their state prior to malware execution, effectively reversing any malware-driven modifications. <--- can restore files encrypted by ransomware.
- Endpoint forensics – graphical reports generated during attacks deliver sandbox equivalent investigative capabilities.

**Details**

- Blocks known in-the-wild threats by leveraging up to the minute cloud intelligence and select reputation services to proactively block threats before they can execute on endpoints.  Think Wild Fire - solution that uses Threat Intelligence data from various sources to provide more update to date reputation to IP address and files.

- Prevents attacks that use memory and application exploits by detecting their execution techniques (e.g., heap spraying, stack pivots, ROP attacks, and memory permission modifications.  Provides kernel level protection to prevent privileged escalation via exploits.

- Stops targeted and zero day attacks using real-time execution monitoring and analysis to assemble true behavioral context without the need for static measures. SentinelOne performs monitoring and analysis of application and process behaviors at low-level instrumentation of OS activities and operations, including memory, disk, registry and network

- Beyond just detection, manual or fully automated mitigation options can be configured via policy and include various actions such as: killing malicious processes, quarantining threats or isolating infected machines.

### SentinelOne (S1) Performance 
 
- CPU = 2%
- Memory = 300mb of ram
- Footprint = 800mb of storage (assuming full logs are enabled)

### Costs(Add Notes)

- Retail $45 per endpoint @3500 endpoints per year
- I have seen 15-17 per endpoint for larger numbers and 3 year term 

## Next Steps(Add Notes)

- We are engaging the vendor for a hands-on review
- Waiting for ISRM's review

## Time-line
