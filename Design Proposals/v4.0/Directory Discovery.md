# Design Proposal: Directory Discovery

## Context
Expanding into the [[Multi-Directory System]] proposal, SocialGuard [[/Concepts/Directory|directories]] should be easily identifiable, and discoverable, which would allow for communication across directories.

## Problem
A [[Concepts/Directory|directory]] has no means to discover another peer directory, short of a swagger page. However, this is not a trustworthy mean of identification.

## Solution 
#v4_0 

### Overview
**The creation of a dedicated endpoint tailored to directory discovery, similar to microservices-style service locators, is a solution.**

### Implementation Conjecture
The endpoint `GET /directory/info`, as URL [`https://api.socialguard.net/api/v4/directory/info`] would return the following content:
```json
{
	"directory": {
		"version": "4.0.0",
		"discoveryEndpoint": "https://api.socialguard.net/api/v4/directory/info",
		"info": {
			"dnsName": "api.socialguard.net",
		}
	}
}
```


