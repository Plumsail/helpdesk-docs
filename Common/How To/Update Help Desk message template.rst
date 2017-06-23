Update help desk message template
#################################

Here you can find how to modify message templates in HelpDesk for Office 365 with adding information from custom columns to message body.

Let’s say you’ve added a custom ‘Order Number’ column to a ticket and now you want to have access to this additional column in notification messages.

Thus your message templates will look like this.

|UpdatedMessage|

First of all, create a new column in help desk Tickets list and place it on the ticket form using `Forms Designer`_.

|TicketForm|

After creating this custom column, switch to `Triggers`_. Triggers are used for notification in help desk, just choose the one which fits your task and go to message templates. In message templates, you can use tokens to access different help desk entities. For example, ``{{Ticket.FieldInternalName}}`` token gives you access to field values of the current ticket.

Note that in order to access the value of a custom column, you need to write column internal name inside token like this ``{{Ticket.OrderNumber}}`` where ‘OrderNumber’ is an internal name of a custom column. If you don’t know the internal name for your column, you need to navigate to Settings –> Edit Column and copy the last part of URL.

|InternalName|

Then go back to Triggers. Now to reference custom field you need to use ``{{Ticket.OrderNumber}}`` token. Paste it in a message template and that’s it. You can also insert any text you like after or before this token. For example, like this:

|TriggerWithUpdatedTemplate|

After saving this message template you will receive e-mails with order numbers in there.


.. |UpdatedMessage| image:: /_static/img/Update-Template1.jpg
   :alt: Example of the upadated message template
.. |TicketForm| image:: /_static/img/Update-Template-2.jpg
   :alt: Ticket
.. |InternalName| image:: /_static/img/Update-Template-3.jpg
   :alt: Internal name of the field
.. |TriggerWithUpdatedTemplate| image:: /_static/img/Update-Template-4.png
   :alt: Additional text in the trigger   


.. _Forms Designer: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Forms%20customization.html
.. _Triggers: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Triggers.html