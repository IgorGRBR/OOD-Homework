# Leanware Project

[![Join the chat at https://gitter.im/kmaooad18/assignment-w11](https://badges.gitter.im/kmaooad18/assignment-w11.svg)](https://gitter.im/kmaooad18/assignment-w11?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

This week's assignment continues the previous one and adds several use cases.

## Enforcing WIP limit

Work-in-progress (WIP) limit helps to keep a small number of features being implemented simultaneously and rather pay attention to completing started work faster than doing a lot at the same time.

This requires to prevent user from starting implementation of more than 2 features at the same time, i.e. when you have 2 features in status `Implementing` and try to start the 3rd you get `400 Bad Request`.

## Collecting and displaying logs

`GET /api/logs`

Returns 10 last log entries.

Every atomic operation that changes state of the system must be logged. For the sake of test check such formats are expected:
- `(Feature|Story) #{id} has been (created|updated|deleted)`
- `Story #{id} has been added to feature #{id}`
- `(Feature|Story) #{id} has been (approved|started|finished)`

Pay attention to the fact that sometimes one incoming request can result in multiple atomic operations, e.g. finishing all stories in a feature means also finishing the feature itself. This has to be logged separately.

## Implementation note

Though not checked explicitly, still try to apply a more careful design and maintain proper domain logic encapsulation and domain invariants. In particular, think about application of terms you learned recently (entities, values, aggregates, aggregate roots). This is neither necessary nor required, but can help you to connect theory to practice. Logging case is also especially illustrative about other general ideas of app decomposition, low/loose coupling and cross-cutting concerns. There are many ways to implement that, and some can be really sophisticated, be sure to find a balanced solution, without being too straightforward yet not doing overengineering prematurely. 


