Version history
###############

Version 2.1.5
-------------

New features:

- Minor improvements.


Version 2.1.3
-------------

New features:

- Simplified widget installation.


Version 2.1.2
-------------

New features:

- Minor fixes and performance optimizations.


Version 2.1.1
-------------

.. important:: This is the major update. It may require manual actions. Follow `this instruction <../How%20To/Upgrade%20to%202-1-1.html>`_ to successfully update HelpDesk to the new version.

New features:

- Tickets list is migrated to Modern UI
- Ticket forms are migrated to Modern UI
- Contacts list is migrated to Modern UI
- Contact forms are migrated to Modern UI
- Right and top navigation are migrated to Modern UI
- HelpDesk now uses `Plumsail Forms <https://plumsail.com/forms/>`_ instead of `Forms Designer <https://spform.com/>`_ for Modern forms customization.

Version 1.5.10
-------------

New features:

- Fixed translation issues in German and Czech.
- Ability to display Plumsail Widget in Swedish.


Version 1.5.9
-------------

New features:

- Fixed search in Requester and Cc fields with more than 5000 contacts.


Version 1.5.8
-------------

New features:

- New trigger action: Set comment type to private.

Version 1.5.7
-------------

New features:

- Fixed translation issues in German, Czech and French.

Version 1.5.6
-------------

New features:

- Ability to display Plumsail Widget in French.

Version 1.5.5
-------------

New features:

- `Custom numbering for tickets`_.
- Bug fix for deleted SLA task issue.
- API settings page localization.
- Other minor bug fixes.

Version 1.5.4
-------------

New features:

- Ability to display Plumsail Widget in Italian.
- Notification about email issues.

Version 1.5.3
-------------

New features:

- Message showing that ticket is viewed by other agents.

Version 1.5.2
-------------

New features:

- Fixed issues with displaying reports in IE.

Version 1.5.1
-------------

New features:

- Scheduler, SLA and Reports: fixed issues related to 5K items limit.

Version 1.5.0
-------------

New features:

- Major stability improvements and optimizations.
- Fix for the issue with slow comment creation.
- Ability to view ticket field changes on the history tab.

Version 1.4.7
-------------

New features:

- Ability to configure displayed fields in tickets list in HelpDesk Widget.

Version 1.4.6
-------------

New features:

- Default ticket views are now working with more than 5000 tickets. 

Version 1.4.5
-------------

New features:

- `REST API`_ and `Power Automate (Microsoft Flow) connector`_ for integration with third-party applications and services. 

Version 1.4.4
-------------

New features:

- Ability to add Plumsail Widget to modern pages.

Version 1.4.3
-------------

New features:

- Ability to display Plumsail Widget in Norwegian and Czech.

Version 1.4.2
-------------

New features:

- Ability to `customize widget forms`_ using Plumsail Forms product.
- New field in tickets list: Support channel.

Version 1.4.1
-------------

New features:

- "Assign to me" button that automatically assigns selected tickets to a current agent.
- Canned responses.
- Ability to change items in home page menu.
- Other minor bug fixes.

Version 1.4.0
-------------

- Implemented a fallback mechanism for notification delivery when event receivers fail.
- Other minor bug fixes.

Version 1.3.5
-------------

New features:

- Ability to display Plumsail Widget in German and Dutch.

Version 1.3.4
-------------

New features:

- Ability to `localize`_ Plumsail Widget.

Version 1.3.3
-------------

New features:

- The `Service Level Agreement feature`_ is implemented. You can define target time and actions to be executed on SLA fail for the following metrics: first reply, next reply, resolution time. Note that ticket status with internal name "Pending" will be used for SLA metrics calculations.


Version 1.3.2
-------------

New features:

- `Ticket splitting`_.
- `Ticket merging`_.

Version 1.3.1
-------------

New features:

- We added prevention of deletion for HelpDesk mailbox field in tickets list.
- Requesters can now leave feedback and rate service on the tickets.
- Other minor bugfixes and performance optimizations.

Version 1.3.0
--------------

New features:

- Major improvements in triggers and scheduler functionality and new user-friendly editor.
- Ability to send emails, start workflows and set ticket fields in the scheduler.
- Other minor bugfixes and performance optimizations.

Version 1.2.13
--------------

New features:

- Ticket resolution date and helpdesk mailbox fields are now visible.
- We added prevention of deletion for mandatory fields in tickets list: Status, Body, Cc, Requester, Assigned to, Subject.

Version 1.2.12
--------------

New features:

- Most of the scripts are moved to CDN.
- Fulltext search is configured for tickets and comments.
- Improved ticket and contact forms, full support of standalone verion of Forms Designer.
- Now you can use standalone Forms Designer with most of its features to customize help desk forms for free. You need to install it from SharePoint store firstly. Embedded version has been excluded from installation.
- Bugfix for 5000 contacts limit.
- Cc from emails are now automatically added to corresponding tickets.
- Other minor bugfixes and perfomance optimizations.

Version 1.2.11
--------------

New features:

- Interface for HelpDesk application `client secret renewal`_.

Version 1.2.10
--------------

New features:

- The `widget`_ for requesters is implemented. A requester can use it to communicate on tickets. It can be placed on any SharePoint site or even to an external site.
- Two new fields to stay up-to-date — Last comment date and Last comment contact.
- Fix for jQuery conflict in ticket body editor.
- Other minor bugfixes.

Version 1.2.9
--------------

New features:

- "HelpDesk mailbox" column has been added to the tickets list. It stores mailbox address from which the original e-mail message was forwarded.

Version 1.2.8
--------------

New features:

- Bugfix for broken SharePoint URLs in e-mail notifications.
- Other minor bug fixes.

Version 1.2.7
--------------

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

.. _rollback forms: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Ticket%20and%20contact%20forms%20customization.html#restore-default-forms
.. _signature: ../User%20Guide/Contacts.html#signature
.. _ticket statuses: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Statuses%20customization.html
.. _trigger engine: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Triggers.html
.. _uninstall page: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Uninstall%20HelpDesk.html
.. _client secret renewal: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Client%20secret%20renewal.html
.. _widget: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Widget.html
.. _Service Level Agreement feature: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/SLA%20policy.html
.. _Ticket splitting: https://plumsail.com/docs/help-desk-o365/v1.x/User%20Guide/Split.html
.. _Ticket merging: https://plumsail.com/docs/help-desk-o365/v1.x/User%20Guide/Merge.html
.. _localize: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Localization.html
.. _customize widget forms: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Widget%20forms%20customization.html
.. _REST API: https://plumsail.com/docs/help-desk-o365/v1.x/API/rest-api.html
.. _Power Automate (Microsoft Flow) connector: https://plumsail.com/docs/help-desk-o365/v1.x/API/ms-flow.html
.. _Custom numbering for tickets: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Ticket%20numbering%20customization.html