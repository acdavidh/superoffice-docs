---
uid: configurable-screens
title: Configurable screens
description: Configurable screens
author: Bergfrid Dias
so.date: 01.02.2024
so.version: 10.2.11
keywords: ui, screen, customization
so.topic: concept
so.audience: settings
so.audience.tooltip: Settings and maintenance
---

# Configurable screens

[!include[Requirement](../../../../../common/includes/req-dev-tools.md)]

Configurable screens enable CRM Administrators to customize SuperOffice CRM user interface controls.

## Which screens can I configure?

* Company
* Contact
* Sale
* Project
* Request
* Follow-up

## What can I customize?

* Modify the default (system) layout of one or more screens for all users to fit the specific needs of your organization.

* Add personalized views for user groups to make them more effective.
* Design layouts optimized for specific project types, sale types, and request types.
* Hide fields that are never used.
* Give easy access to important custom fields.
* Add custom buttons and links. For example, to run a CRMScript.
* Organize custom fields in the **More** tab.
* Add tabs for fields related to a specific area.
* Remove unused tabs.

## Layouts

The default (system) layouts apply to all users until a custom layout is created. [Add custom layouts][2] and assign them to a user group with different needs. Layouts in the **Sales** screen can alternatively be assigned to a **sales type**. Layouts in the **Project** screen can alternatively be assigned to a **project type**. And layouts in the **Request** screen to **request types**.

Layouts have status *published* or *draft*.

![Screen Designer draft layout -screenshot][img1]

![Screen Designer published layout -screenshot][img2]

## More tab

The **More** tab contains all [custom fields][3] ordered by rank. These fields are configurable within this area, and optionally added on other screens.

[User-defined fields][5] (udef) and [extra fields][4] are created as before.

<!-- Referenced links -->
[2]: add-layout.md
[3]: ../../../custom-objects/learn/index.md
[4]: ../../../custom-objects/admin/create-extra-field.md
[5]: ../../../custom-objects/admin/add-udef.md

<!-- Referenced images -->
[img1]: media/status-draft.png
[img2]: media/status-published.png
