# Design Proposal: Multi-Directory System

## Context
As SocialGuard expands into multi-tenancy and an unopinionated approach to security, one of the many concerns addressed regards the currently centralized approach used by SocialGuard, as centralized into [socialguard.net](https://api.socialguard.net). 

**SocialGuard 4.0 should move forward not as an API service, but as an API specification.**

## Problem
Addressing the issue of neutrality and impartiality of the system, having a single actor and [[Concepts/Directory]] makes it clear that a single party is sovereign of all records posted on the [[Concepts/Directory]]. 

SocialGuard should provide an impartial system, where a [[Concepts/Directory]], while governed by its hosting/operating party, is not an absolute source of truth, but relative.

## Solution
#v4_0 

The most effective solution is to design SocialGuard 4.0 around the existence of multiple [[Concepts/Directory|Directories]], and further expand the data structures to prevent collisions and preserve the unicity of information across Directories.

No single [[Concepts/Directory]] should hold any special privilege, or permission over others, within the scope of the SocialGuard v4.0 API specification. Any further implementation should then make note that communication with other Directories is indeed possible.