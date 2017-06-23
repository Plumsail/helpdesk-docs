Track time spent to solve the ticket
####################################

Here you can learn how to configure the view in your HelpDesk for Office 365 where billed hours will be counted for each agent, client, and task.

|Timesheet|

First of all, make some preparations for this case. You need to create a custom column called Billed hours, for example. If you don’t know how to create a new column, `check this article`_. This column will be filled by an agent during closing the ticket.

After you have succeeded in a creation of a column, you need to create a separate list. SharePoint list is sort of container where you put data and where you can filter it with views. Creating a list is quite easy — just click Settings and then choose Site Contents. Then click ‘List’ in the drop-down menu under ‘New’ button.

|NewList|

Type a name for the list and click Create. For this case, you can create Timesheet list with the following structure:

|TimesheetStructure|

You will use Timesheet list later in the workflow which you need to create next. In `this article`_, you can find more details about how to create a new workflow and start it from the trigger.

The use of the workflow is the following — it create an item when the ticket is closed and column Billable Hours filled with the value which is greater than 0.

|NewWorkflow|

After saving a workflow, get back to HelpDesk site and create a trigger which will start the workflow. Navigate to Settings in the navbar and choose Triggers tab. Here you need to create a new item. New trigger will be fired when a ticket has been changed and its status is changed to ‘Solved’. To perform this, use syntax like this:

|Trigger|

In actions was selected ‘Start workflow’ and specified which workflow to start.

After that move back to Timesheet list. You can add another dimension to Timesheet with creating the view. This view will help you to find right data for invoice. Just click ‘Create view’, choose a view type and select columns you would like to display. More about views `here`_.

|newView|

As you need to know the sum of billed hours, select totals to show.

|Totals|

This way you can count every hour spent on the ticket. After it, you can run the workflow which will generate PDF file and send invoices to the clients. Click `this link`_ to know how to generate PDF document using workflow in SharePoint 2013 and Office 365. 

|Result|


.. |Timesheet| image:: /_static/img/timesheet.png
   :alt: Timesheet
.. |NewList| image:: /_static/img/new-list.png
   :alt: New list
.. |TimesheetStructure| image:: /_static/img/timesheet-structure.png
   :alt: Timesheet structure
.. |NewWorkflow| image:: /_static/img/new-workflow.png
   :alt: New workflow  
.. |Trigger| image:: /_static/img/new-trigger-for-billable-workflow.png
   :alt: New trigger
.. |newView| image:: /_static/img/for-invoice-view.png
   :alt: New view
.. |Totals| image:: /_static/img/totals.png
   :alt: Totals
.. |Result| image:: /_static/img/timesheet-result.png
   :alt: Result 

.. _check this article: https://plumsail.com/blog/2016/07/quick-tip-how-to-add-a-new-column-to-tickets-list-and-form-in-sharepoint-help-desk/
.. _this article: https://plumsail.com/blog/2016/08/how-to-start-a-workflow-with-a-trigger-in-sharepoint-help-desk/
.. _here: https://plumsail.com/blog/2016/07/quick-tip-how-to-create-a-new-view/
.. _this link: https://plumsail.com/blog/2014/11/generate-pdf-document-using-workflow-sharepoint-2013-office-365/