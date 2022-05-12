# Consumer Permissions

A **Drupal** module to control user permissions to authenticate with certain consumers.

## :wave: Introduction

:wrench: This module depends on `consumers` and `simple_oauth`. Requires at least `PHP 8.0`.

:warning: This is an **alpha** implementation.  
:warning: It is only tested for the **Authorization Code Grant**.  
:warning: Please be advised that there is no security garantuee.

This module provides permissions to access consumers. Imagine that you want only a certain user group to be able to authenticate with a client. There are two scenarios:
- _The user is already logged in:_ This module changes the access requirements for the `oauth.authorize` route. Only users with the permission to authenticate with the client will be granted access (see `ConsumerPermissionsAccess`).
- _The user is not logged in:_ This module steps in earlier and decorates the user authentication service (see `ConsumerPermissionsAuthDecorator`). The users get direct feedback if they are not allowed to authenticate with the client, because the login will be denied.

## :whale: Usage

After installation you can configure the permissions for existing consumers at:  
`admin/people/permissions/module/consumer_permissions`.  
The permissions will be automatically updated, when consumers are added or deleted.

## :seedling: Contact 

I am open to further develop this module. I would love to discuss your considerations and needs - feel free to contact me.
