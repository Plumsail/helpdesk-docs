Enabling scripting capabilities
####################

We are not able to install HelpDesk unless scripting capabilities are enabled.

If you use tenant administrator account to install HelpDesk, scripting capabilities will be enabled automatically during installation, otherwize, please ask your tenant administrator to install HelpDesk or to turn scripting capabilities on manually. For detail see this `MSDN article`_\.

.. note::
	When you install HelpDesk to Office365 Group site, this site will not appear in SharePoint admin center. Tenant administrator can turn on scripting capabilities by using this PowerShell command:
	::

		Set-SPOsite <SiteURL> -DenyAddAndCustomizePages 0
	Please note that you need to install `SharePoint Online Management Shell`_\.

.. _MSDN article: https://support.office.com/en-us/article/Turn-scripting-capabilities-on-or-off-1f2c515f-5d7e-448a-9fd7-835da935584f
.. _SharePoint Online Management Shell: https://support.office.com/en-us/article/Introduction-to-the-SharePoint-Online-Management-Shell-c16941c3-19b4-4710-8056-34c034493429
