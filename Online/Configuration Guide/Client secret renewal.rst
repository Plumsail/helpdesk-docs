Client secret renewal
#####################

HelpDesk is a provider-hosted SharePoint Add-in. Its remote components interact with SharePoint using OAuth.
To use OAuth, the add-in must be registered with the Azure ACS cloud-based service and the SharePoint App Management Service of the tenancy or farm. 

When add-in is being registered, the following information is specified:

- A GUID for the add-in, called a client ID.
- A password for the add-in, called a client secret.

HelpDesk Add-in only has acces to the site on which it is installed and no other resources.
Add-in secrets expire, thats why we need to renew HelpDesk client secret. For details, see `ContextToken OAuth flow for SharePoint Add-ins`_ and `Replace an expiring client secret in a SharePoint Add-in`_.

Please, renew your client secret on **Settings->About page** to avoid interruption of HelpDesk services.
Your login and password are securely transferred via HTTPS, we don't store your credentials.

|About|

.. note::
    The account used for the client secret renewal should meet the following conditions:

    * it's a **global admin** account;
    * login format is **user@tenant.onmicrosoft.com**;
    * **multi-factor authentication** is disabled;
    * **legacy authentication** is not blocked.

    If the account meets all the conditions and still you can't renew the client secret, try to create a new global admin account.
    After using it for renewing, you can delete the one.

Legacy authentication
+++++++++++++++++++++

To ensure that legacy authentication is not blocked, open Azure Active Directory admin center and check the accordant policy:

|Legacy|

.. _ContextToken OAuth flow for SharePoint Add-ins: https://msdn.microsoft.com/en-us/library/office/fp142382.aspx
.. _Replace an expiring client secret in a SharePoint Add-in: https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/replace-an-expiring-client-secret-in-a-sharepoint-add-in

.. |About| image:: ../_static/img/ConfigurationGuide_ClientSecret_About.png
    :alt: Client secret renewal
.. |Legacy| image:: ../_static/img/ConfigurationGuide_ClientSecret_Legacy.png
    :alt: Legacy authentication blocking