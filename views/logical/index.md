# The Logical View

## Overview

The logical view in EML concerns itself with the functional requirements of an event driven system, and provides a refined structural view of the conceptual elements that are defined in the conceptual view. If the conceptual view focuses on the problem space, then the logical view begins to look at the solution space. Fortunately, due to the composable nature of an event driven approach, the refinement required to describe an event driven system is very narrow and can be summarized as:

- Defining a data model for the events.
- Refining Functions into a logical type of function that indicates its behavioural type.
- Breaking conceptual domains out into channels that define partitioning shemes through keys, along with the transport that will be required to process appropriate events.

## Model

d