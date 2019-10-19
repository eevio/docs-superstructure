### Function

TODO

#### Attributes

Inherits attributes from `DomainUnit`. No further attributes are defined.

#### Associations

Inherits associations from `DomainUnit`. No further associations are defined.

#### Constraints

**(1)** Functions cannot be a realization of an originating function.

```ocl
context Function
  inv: self.realizations->select(unit | unit.oclIsTypeOf(Function))->size = 0
       and self.originations->select(unit | unit.oclIsTypeOf(Function))->size = 0
```

Functions can only influence other units of behaviour by raising further events.

#### Semantics

TODO

#### Notation

TODO
