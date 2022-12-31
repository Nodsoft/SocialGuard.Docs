# Entry

## Definition
A published announcement made by a trusted [[Emitter]], detailing an event that occurred on their platform. 


## Specifications (3.0)
#v3_0 

A trustlist entry follows a basic structure, with parts being omitted during ingest, as these are filled by the receiving [[Directory]], responsible for the good tenure of this entry, and its correlation to existing data.

As SocialGuard 1.0 to 3.0 tied its data to the [Discord](https://discord.com) [[Platform]], all data types are bound to that end.

| Property | Type | Description | Requirement |
| -------- | ---- | ----------- | ----------- |
| `id` | Guid | ID of the entry. | Set by API |
| `userId` | UInt64 | ID of the receiving [[User]]. | Required |
| `entryAt` | DateTime | Date/Time at which the entry was emitted on the [[Directory]]. | Set by API |
| `lastEscalated` | DateTime | Date/Time at which the entry was last escalated/edited. | Set by API |
| `emitterId` | String | ID of the [[Emitter]] responsible for this Entry. | Set by API |
| `emitter` | [[Emitter#Specifications (3.0)]] | Details of the [[Emitter]] responsible for this entry. | Set by API |
| `escalationLevel` | [[#Range: Escalation level (3.0)]] | Escalation/Severity level of the events indicated by this entry. | Required |
| `escalationNote` | String | Details of the event that led to this entry. | Required |

### Range: Escalation level (3.0)
This range defines the severity of an event leading to an entry. It is ranged by severity level and ordered from lowest to highest severity :

1. **Suspicious**
   The [[User]] is marked as suspicious. Their behaviour should be monitored.
2. **Untrusted**
   The [[User]] is marked as untrusted. It is advised to exercise caution when interacting with them.
3. **Blacklisted**
   The [[User]] is deemed dangerous. Banning this user is greatly advised.


