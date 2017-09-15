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

.. _ContextToken OAuth flow for SharePoint Add-ins: https://msdn.microsoft.com/en-us/library/office/fp142382.aspx
.. _Replace an expiring client secret in a SharePoint Add-in: https://msdn.microsoft.com/en-us/library/office/dn726681.aspx