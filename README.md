# Leanware Project

This week's assignment continues the previous one and adds several use cases.

## Features and stories implementation statuses

After feature and connected stories are approved, there is a possibility to start implementing stories.

### Starting story implementation

`POST /api/stories/{id}/start`

`Approved` story can be moved to `Implementing` status. When so, parent feature automatically becomes `Implementing`.

### Finishing story implementation

`POST /api/stories/{id}/finish`

`Implementing` story can be set to `Implemented`. When all feature stories become `Implemented`, feature also becomes `Implemented`.

### Adding more stories to implemented feature

When a story is added to an already implemented feature, feature gets status `ChangeRequested`, and story gets status `Approved`.