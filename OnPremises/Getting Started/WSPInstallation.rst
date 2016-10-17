WSP installation for SharePoint 2013/2016
#########################################

`Download WSP package`_  and place it to one of the servers in your Sharepoint 2013/2016 farm. Run Sharepoint 2013/2016 Management Shell as administrator.

|WspInstallation1|

|WspInstallation2|

Print Add-SPSolution <path to wsp-package>.

|cmd|

Open Central Administration as administrator, then "System Settings" and move to "Manage farm solutions". Select plumsail.helpdesk.wsp and press "Deploy Solution" link.

|SolutionProp|

Go to your application. Select Site Settings item in the root of the site collection. Choose Site collection features in Site Collection Administration section.

|SiteFeatures|

Activate Plumsail HelpDesk feature.

|PFeature|

After that, you can go on to `configuration`_.

.. _Download WSP package: https://plumsail.com/sharepoint-helpdesk/download/
.. _configuration: https://plumsail.com/docs/help-desk-onpremises/v1.x/Getting%20Started/Quick%20HelpDesk%20configuration.html

.. |WspInstallation1| image:: /_static/img/WspInstallation1.png
   :alt: WSP Installation
.. |WspInstallation2| image:: /_static/img/WspInstallation2.png
   :alt: WSP Installation
.. |cmd| image:: /_static/img/cmd.png
   :alt: CMD
.. |SolutionProp| image:: /_static/img/SolutionProp.png
   :alt: Solution Properties
.. |SiteFeatures| image:: /_static/img/SiteFeatures.png
   :alt: Sites Features
.. |PFeature| image:: /_static/img/HD_Feature_2013.png
   :alt: Activate Plumsail Helpdesk
