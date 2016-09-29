Upgrade manager
###############

Upgrade manager allows you to install updates on your HelpDesk. Also, it provides information about HelpDesk version and license. Information about all HelpDesk versions you can find on `Version history`_ page.

Navigate to settings using the icon in the navbar:

|SettingsIcon|

Then click on "About" tab. You will see the interface of upgrade manager.

.. note:: If you don't see "About" tab that means you are using HelpDesk version 1.0.0. You should manually navigate to URL ``<Site with HelpDesk>/HD/Settings/About.aspx``.

|UpgradeManager|

On the picture above you can see that HelpDesk has version 1.2.7 and at the moment this version is up to date. Also you can see that license type is "Production" and the expiration date is 09.12.2016.

If version of your HelpDesk is not up to date and your account have "Manage Web" permissions then you will see the list of updates with full description of each update.

|UpdateAvailable|

To install update you can click "Update" button.


:Manual steps when upgrading from version 1.0: 
You need to perform some actions manually to complete upgrade if you are updating from version 1.0:

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

.. _Version history: ../General/Versionhistory.html
