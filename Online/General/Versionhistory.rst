Version history
###############
Version 1.2.11
--------------

New features:

- Interface for HelpDesk application `client secret renewal`_

Version 1.2.10
--------------

This update can erase some of settings:

- Field and list titles for tickets list will be reset to default.

New features:

- The `widget`_ for requesters is implemented. A requester can use it to communicate on tickets. It can be placed on any SharePoint site or even to an external site.
- Fix for jQuery conflict in ticket body editor.
- Two new fields to stay up-to-date — Last comment date and Last comment contact.
- Other minor bugfixes.

Version 1.2.9
--------------

This update will reset field names for tickets.

New features:

- "HelpDesk mailbox" column has been added to the tickets list. It stores mailbox address from which the original e-mail message was forwarded.

Version 1.2.8
--------------

This update will reset form customizations for tickets and contacts.

New features:

- Bugfix for broken SharePoint URLs in e-mail notifications.
- Other minor bug fixes.

Version 1.2.7
--------------

This update will reset form customizations by applying new text editor.

New features:

- New rich text editor for comments.
- Ability to paste pictures to text editor.
- Ability to upload pictures with drag and drop.
- Guided tour to users on first entrance.
- Getting started video and quick tips in knowlege base.
- Automatic creation of contact on user first visit
- Triggers UI bug fixes.
- Incorrect theme color bug fix.
- Other minor bug fixes.

Version 1.2.6
--------------

This update can erase some of settings:

- Notifications will be disabled during update.
- New tickets and comments creation will not work during update.
- All modifications of triggers will be lost. You will need to configure triggers from scratch.
- New triggers, will not use workflows by default, but you will be able to configure them to use old workflows.
- All modifications of message templates will be lost. You will need to configure them from scratch.
- Field and list titles will be reset to default.
- Forms will be reset to default.

New features:

- Possibility to `rollback forms`_.
- Individual `signature`_ for agent message.
- Localizable `ticket statuses`_.
- New `trigger engine`_ with friendly and flexible interface.
- HelpDesk `uninstall page`_.
- HelpDesk update page.

Version 1.0
------------

- Assign tickets to agents or group of agents.
- Instant appearance of all e-mail messages in help desk
- Filtering tickets with own views.
- Reports section.
- Workflow scheduler and triggers.
- Knowledge base.

.. _rollback forms: Forms%20customization.html#forms-backups
.. _signature: ../User%20Guide/Contacts.html#signature
.. _ticket statuses: Statuses%20customization.html
.. _trigger engine: Triggers.html
.. _uninstall page: Uninstall%20HelpDesk.html
.. _client secret renewal: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Client%20secret%20renewal.html
.. _widget: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Widget.html