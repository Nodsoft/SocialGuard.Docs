# Emitter

## Definition
A trusted party of a [[Concepts/Directory]], responsible for creating new [[Entry|Entries]], based on quantifiable events that impacted their platform.

## Specifications (3.0)
#v3_0

A trustlist emitter follows a standard structure, tied to the [Discord](https://discord.com) API's data structure for its annex properties :

| Property | Type | Description | Requirement |
| -------- | ---- | ----------- | ----------- |
| `login` | String | Key name that represents this emitter on the [[Directory]]. | Required |
| `snowflake` | UInt64 | A [Discord](https://discord.com) snowflake representing this emitter. | Required |
| `emitterType` | [[#Enum: Emitter Type (3.0)]] | Type of emitter. | Recommended |
| `displayName` | String | Display name used to represent this emitter. This can differ from the login, and is only used for UI pruposes. | Optional |

### Enum: Emitter Type (3.0)
As SocialGuard's emitters can be trusted individuals (such as maintainers), or [Discord](https://discord.com) guild/servers, the Emitter Type enum provides a way to make such a distinction.

0. **Unknown**
   Represents an unknown, undefined, or other Emitter profile type.
1. **User**
   Emitter is a singular user.
2. **Server**
   Emitter is a [Discord](https://discord.com) guild/server.