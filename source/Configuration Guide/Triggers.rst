Triggers
########

Triggers allow you to set up automatic execution of arbitrary actions
based on events and conditions. We use it mostly for notifications.
There are bunch of triggers that send email notification based on
specific event type and condition, a list of which you can see on the
screenshot below. But you can use it for other purposes also. Create
your own triggers and run custom actions based on your requirements.

Navigate to settings using the icon in the navbar:

|SettingsIcon|

Then click on “Triggers” tab. You will see the list of predefined
triggers.

|hd-triggers| 

For example there is a built in trigger called “Notification: Requester
– Ticket resolved”. It sends a notification to requester when ticket
status is changed to “Solved”. Let us open this trigger for edit and see
what is inside:

|TriggerNotifyRequester|

This is a description of the fields you can see on the form:

:Name: Trigger title.
:Event_: Type of event when trigger will fired.
:Condition_: Condition which says when actions are to be started. You can find more information about the syntax below.
:Actions_: List of actions that has to be started on the specified event and if the condition is satisfied.

The condition is this:

.. code::

    [Prev::InternalStatus] <> [InternalStatus] and [InternalStatus] = 'Solved'

The condition literally says: **InternalStatus** is changed and **InternalStatus** is equal to “Solved”.

So, you can access field values of tickets and comments using such syntax: ``[InternalFieldName]``.
If the trigger’s event is “:term:`Ticket has been changed`” you can also access previous values like this: ``[prev::InternalFieldName]``.

The actions list contains one action "Send email". Each action in list has short description what it will do. In this trigger action will send email to **requester** and **Cc**.
If you click on action it will be expanded and you will see complete settings of selected action:

|ExpandedAction|

The complete defention of "Send email" action you can find in "Actions_" section.

Events
~~~~~~

.. glossary::

	Ticket has been created 
		Occurs after ticket has been created.
		Trigger with this event **can't refer** to previous values of fields in condition.

	Ticket has been changed
		Occurs after ticket has been changed.
		Trigger with this event **can refer** to previous values of fields in conditions using ``[prev::InternalFieldName]`` syntax.

	Comment has been created
		Occurs after comment has been created.
		Trigger with this event **can't refer** to previous values of fields in condition.

Condition
~~~~~~~~~

In condition allowed to reference to any field of current triggered item (ticket or comment) by internal name. For example ``[Title]`` will return value of **Title** field.
By default lookup field returns **lookup value**, to get **lookup id** you should use ``[LookupFieldName.Id]``.

There is a number of operators and functions available, such as logical operators ``and``, ``or``, ``=``, ``<>``.

For a complete list see `complete condition syntax description`_.

.. toctree::
   :name: triggerstoc
   :maxdepth: 1
   :hidden:

   Condition Syntax

Actions
~~~~~~~

To add new action you can click on "Add new action" link. 

|AddNewAction|

There are three types of actions:

#. `Send Email`_
#. `Start Workflow`_
#. `Set Field`_

List of actions can contain many different actions which will be executed sequentally one after other from top. To reorder actions you can drag action header and drop in desired place.

|DnDAction|

To save changes in trggier you should click "Save" button. To discard any changes you should click "Cancel" button.

Send Email
++++++++++

This action used to send email to different recipients. In message title and body you can use tokens and snippets to automatically include information about current triggered item.

"Send email" action has following setttings:

:To: 
	Required field. Recepients of the message. In this field you can use any contact from contacts list or tokens "All agents", "Requester", "Cc", "Assignee" and "Comment author" (only for ":term:`Comment has been created`" event).
:Except: 
	Contacts from this field will be excluded from recepients list. In this field you can use any contact from contacts list or tokens "All agents", "Requester", "Cc", "Assignee" and "Comment author" (only for ":term:`Comment has been created`" event).
:Subject: 
	Title of message. In this field you can use any context tokens.
:Email body: 
	Body of the message. In this field you can use any context tokens and snippets.
:Attachment URLs: 
	Semicolon separated list of attachment which will be included in the email message. In this field you can use any context tokens. For example ``{{CurrentItem.AttachmentUrls}}``.

Full description of context tokens you can find in `Message templates`_ section.

.. toctree::
   :hidden:
   :maxdepth: 1

   Tokens and snippets

Start Workflow
++++++++++++++

This action used to start selected workflow.

"Start workflow" action has following settings:

:Workflow to start:
	Required field. Name  of the workflow which must be started when trigger fired. Sharepoint Workflows 2010 and Sharepoint Workflow 2013 are supported. You can select list level workflow or site level workflow.

.. toctree::
   :hidden:
   :maxdepth: 1

   Workflow customization

.. seealso::
	HelpDesk Actions Pack is provided with HelpDesk. In `Workflow customization`_ section you can find full description. 

Set Field
+++++++++

This action used to change value of any public field in ticket.

"Set field" action has following settings:

:Field name: Required field. Field name you want to assign a new value.
:Field value: New value which will be assigned to selected field. In this field you can use any context tokens.

.. _Send Email: #send-email
.. _Start Workflow: #start-workflow
.. _Set Field: #set-field
.. _Event: #events
.. _Condition: #condition
.. _Actions: #actions
.. _complete condition syntax description: Condition%20syntax.html
.. _Message templates: Tokens%20and%20snippets.html
.. _Workflow customization: Workflow%20customization.html

.. |SettingsIcon| image:: /_static/img/SettingsIcon.png
   :alt: Settings Navigation Icon
.. |hd-triggers| image:: /_static/img/triggers-0.png
   :alt: HelpDesk Triggers
.. |TriggerNotifyRequester| image:: /_static/img/triggers-1.png
   :alt: Trigger - Notify Requester
.. |ExpandedAction| image:: /_static/img/triggers-2.png
   :alt: Expanded action - Send Email
.. |AddNewAction| image:: /_static/img/triggers-gif-0.gif
   :alt: Add new action
.. |DnDAction| image:: /_static/img/triggers-gif-1.gif
   :alt: Drag and Drop action
