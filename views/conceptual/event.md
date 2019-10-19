### Event

A message that captures the data regarding the change of state within a domain. The originator of the event only knows about the occurrence of the event, and by implication, knows nothing about the causal effect that the event may have.

#### Attributes

Inherits attributes from `DomainUnit`. No further attributes are defined.

#### Associations

Inherits associations from `DomainUnit`. No further associations are defined.

#### Constraints

**(1)** Events cannot be a realization of an originating event in their own domain.

```ocl
context Event
  inv: self.realizations->select(unit | unit.oclIsTypeOf(Event))
         ->forAll(e | e.domain <> self.domain)
       and self.originations->select(unit | unit.oclIsTypeOf(Event))
         ->forAll(e | e.domain <> self.domain)
```

While it is obvious that we want causal connections between events in an event driven system, when considering events that occur within the same domain we want the cause of an event to be driven by some unit of behaviour. 

#### Semantics

There are no specific semantics associated with the conceptual view of an event. It is a placeholder for further refinement in the logical view.

#### Notation

An event is drawn within the boundary of its containing `Domain` as a rectangular box displaying the `TraceableLanguageUnit::name` property.

![Event](../../images/notation-event.png)