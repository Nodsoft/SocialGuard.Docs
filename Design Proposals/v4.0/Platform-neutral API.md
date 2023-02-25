# Design Proposal : Platform-neutral API

## Context
As we expand SocialGuard into an API spec starting with v4.0+, it may be wise to consider other platforms within the scope of the project. 

We currently as of v3.x only support [Discord](https://discord.com) as a [[platform]] for our target [[User|users]]. However, a [[Directory]] should be able to hold [[Record|records]] targeting [[User|users]] from other platforms like [Wargaming](https://wargaming.net), but also regular identifiers such as email and IP addresses.

---

## Problem
The current [[Directory]] system is only scoped to [Discord](https://discord.com), not allowing any further expansion into other platforms.

---

## Solution
#v4_0

### Overview
**SocialGuard 4.0 should be oriented into providing a platform-neutral, unopinionated API specification, allowing for any amount and combination of Platforms to be supported by a [[Directory]].**

### Ramifications and Constraints

#### Database ID Complexity
Developing such a specification may give way to increased complexity in identifying [[User|users]], especially in database, where scalar types often differ between [[platform]]-specific primary keys.

##### Mitigation
Designing the database in a composite-key system might mitigate all possibilities of collisions and/or confusion, however doesn't solve the scalar type mismatch issue for relational databases.

One possible mitigation for DB IDs would be this combination :  

| Column name | Data type | Indexed? |
| ----------- | --------- | -------- |
| PlatformId  | `string`    | Yes      |
| UserId      | `string`    | Yes      |


Using a specific string as a Discriminator for a [[platform]] as the first column, then defining the correct ID for a [[user]] under a universal string-typed second column, this would cover 95% of all possible use cases for any RDBMS used by an API. 

As types are a practical non-issue for any Document-oriented DB system like [MongoDB](https://mongodb.com/), implementations relying on those can use relevant scalar types within their documents.