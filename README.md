# Consumer Permissions

A **Drupal** module to control user permissions to authenticate with certain consumers.

### Introduction

:wrench: This module depends on `consumers` and `simple_oauth`.

:warning: This is a **alpha** implementation. It is only tested for the **Authorization Code Grant**. Please be advised that there is no security garantuee.

:grey_question: This module provides permissions to access consumers. Imagine that you want only a certain user group to be able to authenticate with a client. There are two scenarios:
- _The user is already logged in:_ This module changes the access requirements for the `oauth.authorize` route. Only users with the permission to authenticate with the client will be granted access (see `ConsumerPermissionsAccess`).
- _The user is not logged in:_ This module steps in earlier and decorates the user authentication service (see `ConsumerPermissionsAuthDecorator`). The users get direct feedback if they are not allowed to authenticate with the client, because the login will be denied.

### Usage

:clap: After installation you can configure the permissions for existing consumers at `/admin/people/permissions/module/consumer_permissions`. The permissions will be automatically updated, when consumers are added or deleted.

### Contact 

:seedling: I am open to further develop this module. I would love to discuss your considerations and needs - feel free to contact me.
