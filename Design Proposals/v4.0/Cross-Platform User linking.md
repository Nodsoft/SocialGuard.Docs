# Design Proposal : Cross-Platform User linking

## Context
As we expand SocialGuard into a [[Platform-neutral API]] supporting multiple [[Platform|platforms]], an opportunity arises to identify relations between [[User|users]] across different [[Platform|platforms]]. Namely a [[user]] registering on different [[platform|platforms]] should be identified as the threat is related to the person, not the account (except for hijacking-related situations).

## Problem
When crossing [[Platform|platforms]], [[User|users]] are not identifiable, isolating a danger to an individual's account, rather than an individual itself.

## Solution
#v4_0 

### Overview
Allowing an [[Emitter|emitter]] present and verified across several [[Platform|platforms]] to form quantifiable links between [[User|users]] solves the issue of a cross-platform user account link, by resting that responsibility on the [[emitter]].