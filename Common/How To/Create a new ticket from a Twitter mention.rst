Create a new ticket in HelpDesk from a Twitter mention
######################################################
Social nets are one of the important ways of communicating and networking. Clients ask questions and leave feedback there. To be a successful and caring company it’s a good idea to stay in touch with customers and reply to them as quick as possible. See how you can use `Plumsail Helpdesk connector`_ in Microsoft Flow to create a new ticket in `Plumsail Helpdesk for Office 365`_ when somebody mentioned the company on `Twitter`_.

First, open `Microsoft Flow`_. Then go to My flows tab, click on +New in the left upper corner to build your own workflow.

After that find and select a flow trigger ‘When a new tweet is posted’.

The first step is almost done. Right now, you’ll be automatically offered to log in your twitter account. Then type in the username you want to receive mentions of.

|twitter_mention|

Now it’s time for the second and the last step of the Flow. Click on +New step, find a Plumsail HelpDesk connector and choose the ‘create a new ticket’ action for it. To activate this connection you need an API key. See `here`_ how to get it (mind that now you need an edit type of the key). Copy and paste the API key to the flow.

|api_key|

Then fill out all required fields (Ticket Subject, Body, Requester e-mail, Ticket Assignee Email or SharePoint Group name).

|filling_fields|

Save the flow, and now you’ll receive a new ticket in your HelpDesk every time the company is mentioned on Twitter. It will help you stay in touch with customers and build a productive network.

|new_ticket|

Let us tell `How to send notifications about new tickets to Microsoft Teams and Slack`_. 

.. |twitter_mention| image:: /_static/img/twitter_mention1.jpg
.. |api_key| image:: /_static/img/api_key.jpg
.. |filling_fields| image:: /_static/img/twitter_fillin.jpg
.. |new_ticket| image:: /_static/img/new_ticket_HD.jpg


.. _Microsoft Flow: https://flow.microsoft.com/en-us/
.. _Plumsail Helpdesk connector: https://plumsail.com/docs/help-desk-o365/v1.x/API/ms-flow.html
.. _Plumsail Helpdesk for Office 365: https://plumsail.com/sharepoint-helpdesk/
.. _Twitter: https://twitter.com/
.. _here: https://plumsail.com/docs/help-desk-o365/v1.x/API/get-api-key.html
.. _How to send notifications about new tickets to Microsoft Teams and Slack: https://medium.com/plumsail/how-to-configure-notifications-about-new-tickets-in-microsoft-teams-and-slack-6c5c51901657

