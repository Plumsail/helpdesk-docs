HelpDesk installation
#####################

`Download`_ and run the setup file. Then specify the URL where a
HelpDesk instance will be created and credentials for Full Control
access:

|HelpDeskOnlineInstallAuthentication|

Follow the wizard steps.

.. note::
	If you specify a nonexisting site, it will be created automatically. 
	For example, if you specify *https://yourdomain.sharepoint.com/*\ **HelpDesk**
	and **HelpDesk** doesn’t	exist, it will be created for you. 

.. admonition:: Known issues
	:class: warning

	We are not able to install HelpDesk unless scripting
	capabilities are enabled. Please make sure that you enabled scripting
	capabilities. Read `this article`_ for more information.

Once HelpDesk has been installed, you can go on to `configuration`_.

.. _Download: https://plumsail.com/sharepoint-helpdesk/download/
.. _this article: https://support.office.com/en-us/article/Turn-scripting-capabilities-on-or-off-1f2c515f-5d7e-448a-9fd7-835da935584f
.. _configuration: Quick%20HelpDesk%20configuration.html

.. |HelpDeskOnlineInstallAuthentication| image:: /_static/img/wizard-0.png
   :alt: Install Authentication