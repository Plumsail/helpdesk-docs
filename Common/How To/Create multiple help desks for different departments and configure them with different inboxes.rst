Create multiple help desks for different departments and configure them with different inboxes
##############################################################################################

Let’s say that you have several departments — R&D, HR, and Support. Each of them has unique practices, different e-mail boxes and you want to separate them one from another. Here you can learn how to create multiple help desks and configure them with different inboxes in your service desk.

For that, first of all, you need to create a subsite for each department and then install help desk there.

Note that licensing of Plumsail HelpDesk allows you to install any amount of help desks within one web domain in Office 365 and one server on-premises. Due to it, you can create a separate mailbox for every department, give different permission levels to users and configure an e-mail notification according to needs of a department.

So, navigate to site contents.

|siteContent|

And choose ‘Subsite’ in the drop-down menu.

|Subsite|

Provide title, website address of one department and select a template.  

|SubsiteDetails|

Pay attention to permission settings. Here you can select unique access to a new subsite.

|SubsitePermissions|

And even more — define visitors, members and owners of this site.

|SubsiteVisitors|

New subsite has been created and could be found on the home page in the top link bar.

|TopLinkBar|

After all, just install `Plumsail HelpDesk`_ to your new subsite. When you finish with installation, you can configure forwarding messages from your e-mail address straight to Support help desk. You can find out how to do that in our `documentation`_.

|Email|

Also, you can design triggers for your own needs. For example, you can configure a trigger for notification on special issues. `In this article`_, you can find more information about how to do that.

.. |siteContent| image:: /_static/img/site-content.png
   :alt: Site contents
.. |Subsite| image:: /_static/img/subsite.png
   :alt: Subsite
.. |SubsiteDetails| image:: /_static/img/subsite-details.png
   :alt: Subsite details
.. |SubsitePermissions| image:: /_static/img/subsite-perm.png
   :alt: Subsite permissions
.. |SubsiteVisitors| image:: /_static/img/subsite-visitors.png
   :alt: Subsite visitors
.. |TopLinkBar| image:: /_static/img/top-link-bar.png
   :alt: Top link bar
.. |Email| image:: /_static/img/email-settings-forwarding.png
   :alt: Email settings

.. _Plumsail HelpDesk: https://plumsail.com/sharepoint-helpdesk/download/
.. _documentation: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Email%20settings.html#forwarding-of-e-mail-messages-from-your-support-mailbox
.. _In this article: https://plumsail.com/docs/help-desk-o365/v1.x/How%20To/Add%20new%20email%20notification.html