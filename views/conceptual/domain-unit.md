### DomainUnit

Defines the local concepts associated with a given domain. In the EML conceptual view, these units specialize as events and functions.

#### Attributes

Inherits attributes from `TraceableLanguageUnit`. No further attributes are defined.

#### Associations

- `originations` : `DomainUnit` [0..*]  
The sources of the current domain unit. For example, an event may be the side effect of an invoked function so it will have an origination from that function.

- `realizations` : `DomainUnit` [0..*]  
Represents the domain units that are caused by the current domain unit. For example, a function may yield futher events as a side effect of its invocation.

#### Constraints

No constraints.

#### Semantics

TODO

#### Notation

TODO
