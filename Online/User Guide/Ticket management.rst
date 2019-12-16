Ticket management
#################

.. contents:: Contents
   :local:
   :depth: 1

View ticket
~~~~~~~~~~~

You can open up a ticket  by clicking its title. You will be presented
with a form like this one:

|view-ticket-form|

You can see the Discussion tab with the conversation between agent and
requester. You may notice a small lock underneath an agent’s name, it
tells that this message is a private note that is visible to agents only
and not to the requester. The requester will not receive any
notification about it and will not be able to read it. Also, there is a
list of attachments on the right side of the view, below Due Date.

The ticket's change history can be opened by clicking the History tab:

|history-tab|

Once you opened the ticket form as the assignee, it is marked as read.
But you may want to mark the ticket as unread right from the
form you are currently in. To do this open HelpDesk ribbon tab and click
Mark as unread button (make sure you are the assignee of the ticket).

|mark-unread|

Most of the ticket fields are displayed in the table on the right-hand
side of the screen:

Requester
   The person from the Contacts list who requested the ticket
   (if the contact has his organization specified you’ll see it next to
   his name).

Assigned to
   The SharePoint user that is currently working on the
   ticket.

Cc
   Carbon copy. Contacts specified in this field will receive the
   same notifications as the requester.

Status
   The ticket status. There are four statuses by default: New, In
   progress, Pending and Solved. You can also add your own.

Priority
   Relative ticket priority (Low, Normal, High, Urgent).

Due date
   The date when the ticket has to be resolved by.

Category
   The type of the ticket (Question, Incident, Problem, Request)

Tags
   Some key categories to classify the ticket.

Edit ticket and add comments
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To open the ticket for edit from a display form click the “Edit Item”
button on the ribbon under the “View” tab:

|edit-item|

To open ticket for edit from a list of tickets click the appropriate
button in the context menu:

|edit-ticket-context|

To add a reply or a private note click the “Add reply” or “Add private
note” button and you’ll get to the edit form, where you can enter your
message. Click save and your comment will be added.

|ticket-edit-comment|

Add new ticket
~~~~~~~~~~~~~~

HelpDesk is able to create new tickets from email messages, but you may
need to create a new ticket manually. Click the button in the navigation
bar on the right-hand side of the page:

|new-icon|

When creating a new ticket Title, Requester and Priority fields
are required to be filled in. Status of ticket will be 'New' by design.

|new-ticket-form|

Assign to me button
~~~~~~~~~~~~~~~~~~~

Assign to me button gives you opportunity easily assign Tickets to yourself with one click.

|AssignToMe|

To assign tickets, choose one or several unassigned tickets. Then click on Helpdesk tab and select “Assign to me”. After that, you will find newly assigned tickets on My tickets tab. This action can be reverted. 
If the ticket has been assigned to somebody else, you can reassign it with Assign to me button as well.

|AlreadyAssigned|

.. |AssignToMe| image:: ../_static/img/assign-to-me.jpg
   :alt: Assign to me button
.. |AlreadyAssigned| image:: ../_static/img/assigned-already.jpg
   :alt: Ticket has been already assigned notification


Understanding ticket's statuses
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In HelpDesk you have four built-in statuses: New, In Progress, Pending and Solved. Each of them describes on which stage of resolving is the ticket placed.

|TicketLifecycle|

Statuses **New** and **In Progress** are used for calculations of agent’s work time and resolution time of the ticket. These calculations are needed for metrics ‘First reply time’ and ‘Next reply time’ in `SLA policies`_. SLA is always on pause when the ticket’s status is Pending.
When End-user submits a ticket, ticket’s status will be New by default. It applies to tickets created by team members via HelpDesk interface as well.
Then Agent should provide a reply and change ticket’s status to **Pending**. After End-user has provided some feedback, ticket’s status will be automatically changed into In progress. This cycle can repeat as much as needed to resolve a ticket.
When the ticket is resolved, Agent should change its status to **Solved**.


.. |view-ticket-form| image:: ../_static/img/view-ticket-form.png
   :alt: View Ticket Form
.. |history-tab| image:: ../_static/img/history-tab.png
   :alt: History Tab
.. |mark-unread| image:: ../_static/img/ticket-management-1.png
   :alt: HelpDesk Ribbon Tab
.. |edit-item| image:: ../_static/img/ticket-management-2.png
   :alt: Edit Item
.. |edit-ticket-context| image:: ../_static/img/ticket-management-3.png
   :alt: Edit Ticket Context
.. |ticket-edit-comment| image:: ../_static/img/ticket-edit-comment.png
   :alt: Edit Ticket Comment
.. |new-icon| image:: ../_static/img/new-icon.png
   :alt: New Ticket Navigation Icon
.. |new-ticket-form| image:: ../_static/img/new-ticket-form1.png
   :alt: New Ticket Form
.. |TicketLifecycle| image:: ../_static/img/ticket-cycle.png
   :alt: Ticket lifecycle
.. |TicketStatus| image:: ../_static/img/status-list.png
   :alt: Ticket's statuses


.. _SLA policies: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/SLA%20policy.html