Send SMS notifications from help desk with Microsoft Flow and Twilio
####################################################################

`Microsoft Flow`_ is a service for creation automated workflows between different apps and services. Since now you can connect SharePoint to a lot of external services, so you can do with Plumsail HelpDesk for Office 365. Let’s connect HelpDesk to Twilio. In this use case, agents will get SMS every time when a ticket has been assigned to them.

First of all, you need to create a free account in Microsoft Flow. After your account has been created, Microsoft Flow could be found in the waffle icon in the Office 365 suite bar.

|SuiteBar|

Click on this icon and you will be redirected to Flow site. Now you are ready to create a customized flow. Navigate to My Flows and then choose Create from blank. Provide a name for your workflow and choose one of the triggers. In this case, it’s trigger for SharePoint which will be fired when an existing item is modified. Once you have selected SharePoint, you will need to log in. And don’t forget to choose the list from which data will be retrieved.

|FirstAction|

After creating the first step continue with creating an additional condition. Just click to Next step button and choose Add a condition. Here you need to choose ‘Edit in advanced mode’ and be ready to provide some coding.

.. code::

     @and(not(empty(triggerBody()?['AssignedTo']?['Email'])),
     equals(triggerBody()?['Is_x0020_notified'], bool(0)))

Literally, it says that ‘Assigned to’ field shouldn’t be empty and ‘Is notified’ field is unchecked.

As you want to receive a SMS only once, you have to create a custom field — ‘Is notified’. By default, it is unchecked. The value is stored as a boolean, so the field value will be false. 

To make your code work, you need to use an expression with bool(0) as engine converted it to ‘false’ only that way.

|Condition|

And finally, you are creating the last step of the flow. You don’t know exactly yet to whom will be assigned a ticket, so that’s you are creating an action with Office 365 which will get user profile from ‘Assigned to field’.

|GetUser|

And If a ticket was assigned to someone, the second action will happen. Twilio will send a message to an agent with some text. The telephone number of an agent will be retrieved from Office 365 user profile (if it is provided).

|Twilio|

The last action of the last step — updating ‘Is notified’ field in SharePoint as you probably don’t want to bombarding agents about any updates of a ticket. For that choose ‘Update item’ and provide required details.

|UpdateItem|

Save flow and that’s it! It starts running immediately, so you can check how it’s working. 

.. |SuiteBar| image:: /_static/img/flow-button.png
   :alt: Office 365 suite bar
.. |FirstAction| image:: /_static/img/flow-action-1.png
   :alt: SharePoint action in Flow
.. |Condition| image:: /_static/img/flow-condition.png
   :alt: Condition
.. |GetUser| image:: /_static/img/get-user-ptofile.png
   :alt:  Get user profile action 
.. |Twilio| image:: /_static/img/twilio-action.png
   :alt: Action with Twilio
.. |UpdateItem| image:: /_static/img/update-item.png
   :alt: Update item action
.. || image:: /_static/img/
   :alt: 


.. _Microsoft Flow: https://flow.microsoft.com/en-us/