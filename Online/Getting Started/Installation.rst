HelpDesk installation
#####################

.. raw:: html
   <div data-nosnippet="true"<iframe width="840" height="472" src="https://www.youtube.com/embed/39pH5_LgElw" frameborder="0" 
   allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

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

Unfortunately, sometimes SharePoint Online experiences outages.
Incidents that affect Office 365 or SharePoint Online can hinder to install HelpDesk.

Please check the `health status`_ of Office 365 services ("Health" feature of Microsoft 365 admin center).
If there are problems that affect the specified services, wait until they are resolved and try to install HelpDesk again.

.. _Download: https://plumsail.com/sharepoint-helpdesk/download/
.. _this article: ../Configuration%20Guide/Enabling%20scripting.html
.. _configuration: Quick%20HelpDesk%20configuration.html
.. _health status: https://admin.microsoft.com/Adminportal/Home#/servicehealth

.. |HelpDeskOnlineInstallAuthentication| image:: ../_static/img/wizard-00.png
   :alt: Install Authentication

.. |HelpDeskOnlineInstallSiteName| image:: ../_static/img/wizard-1.png
   :alt: HelpDesk Site Name