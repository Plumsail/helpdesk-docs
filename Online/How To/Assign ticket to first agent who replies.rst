Assign ticket to first agent who replies
########################################

It is very897 common to have a lot of agents responsible for the customer support inside a company. And with a lot of tickets coming in, it may be hard to specify which agent should be the responsible for each ticket manually. An alternative is to assign a ticket to whichever agent replies to it first automatically and this article will describe how to do it.

First of all, log into your Help Desk instance, and go to “Settings” on the right.

|image-1| 

Now, find the “Triggers” tab and click on that.

|image-2|

This is where we create actions to be done whenever a rule or an event is fulfilled. We’ll need to create a trigger for when a new comment is created. With this trigger we’ll set the comment creator to be the assignee of this ticket, but only if the ticket still has no assignee and the ticket wasn’t created for the requester either.

Let’s start creating the trigger by clicking on “new item” on the top.

|image-3|

On the “New trigger” page, choose a name for your trigger and set it so it runs when a new comment is created.

|image-4|

Now, you should set up those conditions that we mentioned earlier. We want to affect only tickets with no assignee and we want to run this trigger only if the person who sent the comment isn’t the requester.
That is easy with HelpDesk! First add the condition so the assignee e-mail of the ticket is empty. Make sure you put the empty ‘’ on the right.

|image-5|

Then add the condition so the comment didn’t come from the requester.

|image-6|

You can even validate your conditions to make sure everything’s right.

|image-7|

Next thing is adding the action that will set the assignee properly. Add a new action pressing “add action”.

|image-8|

This will be a “Set field” action. Set it so HelpDesk will change the “Assigned To” field to {{Comment.From.Email}}. This way it will assign the ticket to the agent who replied to it.

|image-9|

And this is how you can automatically assign tickets to the first agent who replies to it. This can be done in both SharePoint Online and SharePoint 2013/2016.

.. _From ribbon: #from-ribbon
.. _From site settings: #from-settings

.. |image-1| image:: /_static/img/assign-ticket-to-agent-who-replied/1.png
   :alt: Settings button
.. |image-2| image:: /_static/img/assign-ticket-to-agent-who-replied/2.png
   :alt: Triggers tab
.. |image-3| image:: /_static/img/assign-ticket-to-agent-who-replied/3.png
   :alt: New item
.. |image-4| image:: /_static/img/assign-ticket-to-agent-who-replied/4.png
   :alt: New trigger
.. |image-5| image:: /_static/img/assign-ticket-to-agent-who-replied/5.png
   :alt: First condition
.. |image-6| image:: /_static/img/assign-ticket-to-agent-who-replied/6.png
   :alt: Second condition
.. |image-7| image:: /_static/img/assign-ticket-to-agent-who-replied/7.png
   :alt: Validate conditions
.. |image-8| image:: /_static/img/assign-ticket-to-agent-who-replied/8.png
   :alt: Add action
.. |image-9| image:: /_static/img/assign-ticket-to-agent-who-replied/9.png
   :alt: Set field