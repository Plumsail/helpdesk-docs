HelpDesk installation
#####################

`Download`_ and run the setup file.

Then specify your SharePoint tenant URL where a HelpDesk instance will be created:

|HelpDeskOnlineInstallAuthentication|

You will be prompted for your credentials. Please enter the **tenant admin** credentials.

Then you'll be asked to choose the HelpDesk site name, languange and privacy settings:

|HelpDeskOnlineInstallSiteName|

Your HelpDesk site will be available under: **yourdomain**.sharepoint.com/sites/**sitename**

Once HelpDesk has been installed, you can go on to `configuration`_.

Known Issues
++++++++++++

During installation, you can encounter some issues whether with creating a SharePoint site or with deploying different elements of HelpDesk.
In such a case, just click "Try again" button of the wizard to repeat the failed steps.
Frequently, the installation fails because of temporary problems on SharePoint side so if the previous step doesn't help, try to check `health status`_ of Office 365 services.
If there are incidents which affect Office 365 or SharePoint Online services, wait until they are resolved and try to install HelpDesk again.

.. _Download: https://plumsail.com/sharepoint-helpdesk/download/
.. _this article: ../Configuration%20Guide/Enabling%20scripting.html
.. _configuration: Quick%20HelpDesk%20configuration.html
.. _health status: https://admin.microsoft.com/Adminportal/Home#/servicehealth

.. |HelpDeskOnlineInstallAuthentication| image:: ../_static/img/wizard-00.png
   :alt: Install Authentication

.. |HelpDeskOnlineInstallSiteName| image:: ../_static/img/wizard-1.png
   :alt: HelpDesk Site Name