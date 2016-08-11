Upgrade manager
###############

Upgrade manager allows you to install updates on your HelpDesk. Also, it provides information about HelpDesk version and license.

Navigate to settings using the icon in the navbar:

|SettingsIcon|

Then click on "About" tab. You will see the interface of upgrade manager.

.. note:: If you don't see "About" tab that means you are using HelpDesk version 1.0.0. You should manually navigate to URL ``<Site with HelpDesk>/HD/Settings/About.aspx``.

|UpgradeManager|

On the picture above you can see that HelpDesk has version 1.2.6 and at the moment this version is up to date. Also you can see that license type is "Production" and the expiration date is 09.12.2016.

If version of your HelpDesk is not up to date and your account have "Manage Web" permissions then you will see the list of updates with full description of each update.

|UpdateAvailable|

To install update you can click "Update" button.

Upgrade to version 1.2.6
------------------------

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

Manual steps
~~~~~~~~~~~~

You need to perform some actions manually to complete update:

1. Download CSS file :download:`plumsail.helpdesk.theme.css </_static/download/plumsail.helpdesk.theme.css>`.
2. **Upload** and **publish** "plumsail.helpdesk.theme.css" to following location ``<Site Collection with HelpDesk Site>/Style Library/<your language folder>/Themable/Plumsail/HelpDesk``.

	.. note::
		| If HelpDesk is installed on the site ``https://helpdesk.sharepoint.com/sites/IT/HelpDesk/`` with **English** as default language 
		| then you should **upload** and publish the file to ``https://helpdesk.sharepoint.com/sites/IT/Style Library/en-us/Themable/Plumsail/HelpDesk``.

3. Go to site settings and click "Change the look".
4. Reapply your current look.

.. |SettingsIcon| image:: /_static/img/settingsicon.png
   :alt: Settings Navigation Icon
.. |UpgradeManager| image:: /_static/img/upgrade-manager-0.png
   :alt: Upgrade Manager
.. |UpdateAvailable| image:: /_static/img/upgrade-manager-1.png
   :alt: Update Available

.. _rollback forms: Forms%20customization.html#forms-backups
.. _signature: ../User%20Guide/Contacts.html#signature
.. _ticket statuses: Statuses%20customization.html
.. _trigger engine: Triggers.html
.. _uninstall page: Uninstall%20HelpDesk.html
