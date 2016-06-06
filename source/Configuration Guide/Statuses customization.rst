Statuses customization
######################

You can translate ticket statuses into your native language. 
All ticket statuses are saved in "Ticket Statuses" list which you can find in "Site Contents" page.

|TicketStatusesList|

Each status has two fields:

:Name: Display name of the status. All agents will see this value in "Status" field of ticket.
:Internal Name: Internal name of the status. This field used by HelpDesk system. This field might be usefull in triggers. Each ticket refer to this field by ``[InternalStatus]`` field.

By default there are three statuses and two of them are system statuses ("New" and "Solved"). System status means that you can't change value of "Internal Status" field.

To translate display name of the status you can edit list item and change "Name" field.

|EditStatus|

.. |TicketStatusesList| image:: /_static/img/ticket-statuses-0.png
   :alt: Ticket Statuses List
.. |EditStatus| image:: /_static/img/ticket-statuses-1.png
   :alt: Edit ticket status
