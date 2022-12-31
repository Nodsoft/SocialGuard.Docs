# Record

## Definition
A collection of [[Entry|Entries]] relating to the same [[User|User]] held by a [[Directory]]. 


## Specifications (3.0)
#v3_0 

A record is only a carrier for multiple [[Entry|Entries]], and thus follows a simple pattern: 

| Property | Type | Description | Requirement |
| -------- | ---- | ----------- | ----------- |
| `id` | UInt64 | ID of the [[User]] this Record references. | Required |
| `entries` | Array: [[Entry#Specifications (3.0)]] | A collection of [[Entry]] objects referencing the queried [[User]]. | Required |
