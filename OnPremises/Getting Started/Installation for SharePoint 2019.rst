HelpDesk installation for SharePoint 2019
#########################################

`Download`_ and run it on one of the servers in your SharePoint 2019 farm as Farm Administrator. Follow the wizard steps.

Go to SharePoint site where you want to create HelpDesk. Select ‘Site Settings’:

|HelpDeskAuthentication|

Then navigate to site features:

|HelpDeskAuthentication1|

Activate Plumsail HelpDesk feature.

|HelpDeskFeature| 

Once you clicked on the feature you are redirected to installation wizard. It will check prerequisites and show you such screen:

|HDInstaller|

Then click next and wait for installation. Once HelpDesk has been installed, you can go on to `configuration`_.

WSP installation for SharePoint 2019
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

`Download WSP package`_  and place it to one of the servers in your Sharepoint 2019 farm. Run Sharepoint 2019 Management Shell as administrator.

|Shell|

|RunAs|

Type Add-SPSolution <path to wsp-package>.

|Command|

Open Central Administration as administrator, then "System Settings" and move to "Manage farm solutions". Select plumsail.helpdesk.wsp and press "Deploy Solution" link.

|Deployment|

Go to your application. Select Site Settings item in the root of the site collection. Choose Site collection features in Site Collection Administration section.

|SiteFeatures|

Activate Plumsail HelpDesk feature.

|PFeature|

After that, you can continue with `configuration`_.

.. _Download: https://plumsail.com/sharepoint-helpdesk/download/
.. _this article: https://technet.microsoft.com/en-us/library/jj219638.aspx
.. _Download WSP package: https://plumsail.com/sharepoint-helpdesk/download/
.. _configuration: https://plumsail.com/docs/help-desk-onpremises/v1.x/Getting%20Started/Quick%20HelpDesk%20configuration.html

.. |HelpDeskAuthentication| image:: ../_static/img/HD_SiteSettings_2013.png
   :alt: Site settings
.. |HelpDeskAuthentication1| image:: ../_static/img/ManageSiteFeatures.png
   :alt: Site Features
.. |HelpDeskFeature| image:: ../_static/img/HD_Feature_2013.png
   :alt: Activate Plumsail HelpDesk
.. |HDInstaller| image:: ../_static/img/installer.png
   :alt: HelpDesk Installer
.. |Shell| image:: ../_static/img/GettingStarted_InstallationSP2019_Shell.png
   :alt: Starting of SharePoint Mangement Shell
.. |RunAs| image:: ../_static/img/GettingStarted_InstallationSP2019_RunAs.png
   :alt: Running as administrator
.. |Command| image:: ../_static/img/GettingStarted_InstallationSP2019_Command.png
   :alt: Management Shell command
.. |Deployment| image:: ../_static/img/GettingStarted_InstallationSP2019_Deployment.png
   :alt: Solution deployment
.. |SiteFeatures| image:: ../_static/img/SiteFeatures.png
   :alt: Sites Features
.. |PFeature| image:: ../_static/img/HD_Feature_2013.png
   :alt: Activate Plumsail Helpdesk