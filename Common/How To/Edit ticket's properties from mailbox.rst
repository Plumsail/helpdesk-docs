Edit ticket's properties from mailbox
#####################################

You can work with Plumsail HelpDesk for Office 365 from your mailbox but not only respond to tickets. For example, you can edit and update some ticket's properties.

For instance, let's check how assignee can change ticket’s status, resolve it or update its priority straight from the mail.

All of these can be performed with the help of `triggers`_. For example, you’d like to create a trigger which will change priority status of the ticket with a short message like #high-priority.

For that, you need to navigate to Settings and then click Triggers tab. To create a new trigger choose New item. The ‘Event’ field specifies an action that you want the trigger to perform, as you want it to occur only when a comment has been created, you choose that option in the drop-down menu. ‘Conditions’ field defines the conditions which should be met in order for the action to be performed. Here you specify that comment should contain hashtag high-priority.

|EditTrigger|

After you have set up a condition, it’s time to define an action. Choose ‘Set field’ action, pick ‘Priority’ field and provide its value. Then save the trigger.

|Action|

It is working in the following way: you sent a response to some ticket only with one hashtag. 

|Letter|

As usual, it was converted into a comment. 

|Comment|

Thus, ticket’s priority was updated.

|TicketUpdate|

In the same way, you can resolve the ticket.

|Resolved|

Or change ticket’s category.

|TicketCategory|

.. |EditTrigger| image:: /_static/img/ticket-high-priority.png
   :alt: Edit trigger
.. |Action| image:: /_static/img/set-priority-action.png
   :alt: Set action
.. |Letter| image:: /_static/img/how-to-letter.png
   :alt: Letter with hashtag
.. |Comment| image:: /_static/img/letter-2.png
   :alt: Comment from mailbox
.. |TicketUpdate| image:: /_static/img/ticket-update.png
   :alt: Ticket was updated
.. |Resolved| image:: /_static/img/ticket-resolved.png
   :alt: Ticket resolved   
.. |TicketCategory| image:: /_static/img/ticket-category.png
   :alt: Ticket category
.. || image:: /_static/img/
   :alt:   
.. || image:: /_static/img/
   :alt:   
.. || image:: /_static/img/
   :alt:   
.. || image:: /_static/img/
   :alt:   


.. _triggers: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Triggers.html