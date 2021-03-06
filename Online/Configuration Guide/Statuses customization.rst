Statuses customization
######################

.. contents:: Table of contents
   :local:
   :depth: 1

.. _statuseslist:

Ticket Statuses list
~~~~~~~~~~~~~~~~~~~~~

You can translate ticket statuses into a language other than English. All ticket statuses are stored in the "Ticket Statuses" list that could be found in the "Site Contents" page.

|TicketStatusesList|

Each status has two fields:

:Name: A display name of the status. This value is displayed in the UI: views, forms and etc.
:Internal Name: An internal name of the status that is used in triggers, e-mail synchronization, and other core processes.

By default, there are three statuses and two of them are "system" ("New" and "Solved"). "System" status means that you cannot remove it or change its "Internal Status" field.

To translate the statuses, change their "Name" field.

|EditStatus|

.. _how-connected:

How Statuses list is connected to Tickets list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

As it was said above, "Ticket Statuses" list has two fields — **Display Name** and **Internal Name**. These fields are correlating with fields from "Tickets" list. There could be found two fields: **Status** and **Internal Status**.
Status field gets its value from Display Name and Internal Status gets information from Internal Name.

Look at this picture to understand how fields are connected.

|TicketToStatus|


.. _Ticket Statuses list: #statuseslist
.. _How Statuses list connected to Tickets list: #how-connected

.. |TicketStatusesList| image:: ../_static/img/ticket-statuses-0.png
   :alt: Ticket Statuses List
.. |EditStatus| image:: ../_static/img/ticket-statuses-1.png
   :alt: Edit ticket status
.. |TicketToStatus| image:: ../_static/img/TicketToStatus.png
   :alt: From Tickets to Statuses

