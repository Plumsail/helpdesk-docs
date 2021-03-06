Scheduling of tasks and reminders
#################################

Scheduler allows you to set up different actions on unsolved tickets which have been changed during last 30 days.

Navigate to settings using the icon in the navbar:

|SettingsIcon|

Here is the pre-defined scheduler task in HelpDesk:

|HelpDeskScheduler|

It is a task which will notify assignees about overdue tickets every morning. Let’s open this task and see what’s inside.

|TaskCondition|

Task's form fields: 
 
:Task name:  Provide a title for a task. 
:Description: Provide some information about this task.

Below we see three tabs: schedule, task, and logs.

On the schedule tab, you choose the period of time when a notification is performed. 

|Schedule|

.. note::
   You can schedule a task not oftener than once in an hour.

On the second tab, you need to provide a condition for a task.

|Task|

`Condition syntax`_ and `actions`_ are exactly the same as in triggers, visit these links to learn more. 
 
The list of actions contains three types of actions: send email, start workflow and set field. One of them will be executed if the condition is "true".

|Task1|

To test any task, you can run it manualy on the "Scheduler" tab.

|RunTask|

On the logs tab you can find history on what tickets task were performed. As well, you can find this information in the ticket history if you check "Log task runs in the ticket history" option on the schedule tab.

|Logs|

.. _Condition syntax: Condition%20syntax.html
.. _actions: General%20information.html#actions

.. |SettingsIcon| image:: ../_static/img/settingsicon.png
   :alt: Settings Navigation Icon
.. |HelpDeskScheduler| image:: ../_static/img/overdueNotification.png
   :alt: Overdue notification task
.. |TaskCondition| image:: ../_static/img/task-condition.png
   :alt: Task condition
.. |Schedule| image:: ../_static/img/runat.png
   :alt: Schedule tab
.. |Task| image:: ../_static/img/task-condition-1.png
   :alt: Condition for task
.. |Task1| image:: ../_static/img/task-action.png
   :alt: Condition for task
.. |Logs| image:: ../_static/img/task-logs.png
   :alt: Task's logs
.. |RunTask| image:: ../_static/img/ConfGuide_Scheduler_RunTask.png
   :alt: Run a task