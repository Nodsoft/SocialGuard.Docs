# Design Proposal : URI Keys

## Context
As we expand into decentralising SocialGuard into a [[multi-Directory system]], we're bound to see the basic JSON structures expand out of basic scopes defined in the SocialGuard API spec, following each API implementer's needs.

## Problem
API implementers may want to expand the JSON structures, using custom properties. For non-standard keys that haven't been agreed upon prior through API specs, collisions can happen on shorter keys with industry-standard names, where formats and implementation-specific standards can overlap.

## Solution
#v4_0 

### Overview
A widely-adopted industry solution consists of using URIs as property names, in place of arbitrarily-defined names.

### Implementation
Taking an example from an Emitter DTO, defined as so, as of version 3.x :
```json
{
  "login": "Sakura",
  "emitterType": 2,
  "snowflake": 278265197280362500,
  "displayName": "Sakura Akeno Isayeki"
}
```

We could assert a URI-based property naming system to mutate the DTO as so :
```json
{
  "https://socialguard.net/ref/emitter/login": "Sakura",
  "https://socalguard.net/ref/emitter/extensions/discord/type": 2,
  "https://discord.com/developers/docs/reference#snowflakes": 278265197280362500,
  "https://socialguard.net/ref/emitter/displayName": "Sakura Akeno Isayeki"
}
```

While the solution above provides a collision-less system, allowing most implementers to provide heir own solutions through their own domains, this means unnecessarily multiplying the size/length of property names, with little benefit for API-standard keys.


