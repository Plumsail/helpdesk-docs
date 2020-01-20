Reassign ticket from disabled user
###############################################

First thing when an agent leaves team of your service desk is ensure that all open tickets will be handled by someone else in the team. To automate this process, you can use `Scheduler`_ for reassigning tickets from the disabled user. Here you can learn how to do that.

First of all, you need to `configure synchronization of your Office 365 accounts with HelpDesk`_. You need this for checking if account is enabled or not.

Then navigate to  **Settings**. 
Navigate to the **Scheduling** tab. Here you can find pre-defined task but you need to create a new one, so click on ‘Add new task’.

|schedulerOverview|

Provide a title for your task and schedule how often you want to run that task. On the screenshot, it was chosen to repeat it every day. 

|schedulerTask|

After you finish with scheduling, you need to configure a task. Here you need to provide a simple condition. Literally, it says that ticket’s field ‘Is enabled’ should contain false value (which equals to ‘No’) and the ticket should be unsolved. Note that ‘Is enabled’ is a custom field which were created manually in Contacts list. `Here`_ you can find how to do that.

|schedulerCondition|

Then you need to specify which action to perform, in this case, it is ‘Set field'.

In the drop-down menu select ‘Assigned to’ field and provide a username to whom will be reassigned all tickets from disabled user.

|SetField|

Save changes and run a task to test it. You can make sure that your task is working by looking in the logs. 


.. |schedulerOverview| image:: ../_static/img/scheduler-overview.png
   :alt: Scheduler overview
.. |schedulerTask| image:: ../_static/img/scheduler-task.png
   :alt: Scheduler task
.. |schedulerCondition| image:: ../_static/img/scheduler-condition.png
   :alt: Scheduler condition
.. |SetField| image:: ../_static/img/scheduler-action.png
   :alt: Set action

.. _Scheduler: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Scheduling.html 
.. _Here: https://plumsail.com/docs/help-desk-o365/v1.x/How%20To/Add%20new%20column%20to%20tickets%20list.html  
.. _tokens: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Tokens%20and%20snippets.html
.. _configure synchronization of your Office 365 accounts with HelpDesk: https://plumsail.com/docs/help-desk-o365/v1.x/How%20To/Sync%20SharePoint%20user%20profiles%20fields%20to%20HelpDesk%20contacts.html