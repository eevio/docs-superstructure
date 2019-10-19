### Event

TODO

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

TODO

#### Notation

TODO
