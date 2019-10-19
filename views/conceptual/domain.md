### Domain

A `Domain` defines a tangible and logical boundary of applicability within an event driven software system.

#### Attributes

Inherits attributes from `TraceableLanguageUnit`. No further attributes are defined.

#### Associations

- `events` : `Event` [0..*]  
The events that are applicable within the associated domain.

- `functions` : `Function` [0..*]  
Represents notional units of behaviour that are relevant within the associated domain.

#### Constraints

No constraints.

#### Semantics

With Domain Driven Design ("DDD") as context, we can consider a _domain_ as representing something in the _problem_ space that is to be addressed with a software effort. Furthermore, domains can be decompossed into sub-domains which typically reflect some organizational structure and scope. It is at this level that an EML `Domain` would operate.

Decomposition, especially in an enterprise setting, is important because modeling large domains gets progressively harder when working within a single model. DDD recognizes that a single unified model of an entire business is not feasible or even cost effective, and so introduces decomposition through _sub-domains_ and _bounded contexts_. Each sub-domain can have its own unified model and describe both unrelated or local concepts, alongside shared or common concepts with mechanisms to map between them for integration purposes.

The EML approaches decomposition by allowing domains to be decomposed into multiple _local_ domains that describe local events of interest, and by supporting references to _external_ domains that provide integration with shared or common events that fulfill an overall business need.

In a supporting EML Logical View, a conceptual local domain can be refined into one or more channels which is akin to a _bounded context_. Ultimately, a sub-domain (or EML `LocalDomain`) aims to delimit the applicability of a broader business domain, while a bounded context (or EML `Channel`) delimits the applicability of the sub-domain. Domains are defined within the problem space, while bounded contexts operate within the solution space.

#### Notation

`Domain` is an abstract concept that has a visual notation that is defined by `LocalDomain` and `ExternalDomain`.
