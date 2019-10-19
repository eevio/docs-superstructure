### DomainUnit

Defines a local concept that is associated with a domain. In the EML conceptual view, these units specialize as `Event` and `Function`.

#### Attributes

Inherits attributes from `TraceableLanguageUnit`. No further attributes are defined.

#### Associations

- `domain` : `Domain` [1]  
 The domain that the current domain unit belongs to.

- `originations` : `DomainUnit` [0..*]  
The sources of the current domain unit. For example, an event may be the side effect of an invoked function so it will have an origination from that function.

- `realizations` : `DomainUnit` [0..*]  
Represents the domain units that are caused by the current domain unit. For example, a function may yield futher events as a side effect of its invocation.

#### Constraints

No constraints.

#### Semantics

The originations and realizations of all the `DomainUnit` within a given domain defines the order of activity within that domain. When combined with other domains, including those that are `ExternalDomain`, it is possible to view and reason about activity in a much broader context including the entire enterprise for example.

Given the cyclic nature of the originations and realizations associations it is easier to reason about them as an eventual graph of domain units. These associations may be intrinsically used by a specialization; `Function` for example will require knowledge of which originating events it should respond to.

#### Notation

The notation for `Event` and `Function` are defined seperately, however, a domain unit is drawn within the boundary of its associated `Domain`.

The originations and realizations associations are used to layout the domain units within their domain in the order that they are encountered. For domain units having multiple realizations (`self.realizations->size > 1`), those realized domain units will be stacked vertically in no particualr order. Finally, thin connecting lines between the originating and realized domain units are used to represent the association.

![Domain Unit Associations](../../images/notation-domain-unit-ordering.png)

