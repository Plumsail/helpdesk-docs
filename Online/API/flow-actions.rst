Plumsail HelpDesk connector
==================================

This connector helps you to manipulate data in your HelpDesk with the help of Microsoft Flow. Before starting, ensure that you `added Plumsail HelpDesk connector to Microsoft Flow <../api/use-from-flow.html>`_.

.. contents:: List of actions in this connector
   :local:
   :depth: 1

Get tickets
----------------------------------

Get tickets. By default this actions returns first 50 tickets.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Tickets
       -  The array of ticket objects
       -  .. code-block:: json

       		[
			  {
			    "subject": "Site issues",
			    "requester": {
			      "id": 2,
			      "title": "John Davis",
			      "email": "j.davis@example.com",
			      "spUserId": null,
			      "role": "End-User",
			      "emailAlternate": null,
			      "customFields": {}
			    },
			    "assignedTo": {
			      "id": 1,
			      "title": "Mary Smith",
			      "email": null,
			      "spUserId": 11,
			      "role": "Agent",
			      "emailAlternate": null,
			      "customFields": {}
			    },
			    "status": "In progress",
			    "category": "Question",
			    "priority": "High",
			    "dueDate": "2018-04-27T13:10:02Z",
			    "created": "2018-04-27T13:10:05Z",
			    "resolutionDate": "0001-01-01T00:00:00",
			    "cc": [],
			    "tags": [],
			    "attachments": null,
			    "id": 1,
			    "customFields": {}
			  }
			]

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  includeAttachments
       -  By default result will not contain any attachments. To load ticket attachments you must set parameter "includeAttachments" to Yes.
       -  Yes
    *  -  $select
       -  An `ODATA`_ $select query option to specify which fields to return for a list item. You can use * to return all available fields.
       -  SupportChannel,HelpDeskMailbox,Metadata/IsRead
    *  -  $expand
       -  An `ODATA`_ $expand query option to specify that the request returns the values of lookups.
       -  Metadata
    *  -  $filter
       -  An `ODATA`_ $filter query option to restrict the entries returned
       -  Priority eq 'High'  
    *  -  $orderBy
       -  An `ODATA`_ $orderBy query option for specifying the order of entries.
       -  ID desc  
    *  -  $top
       -  An `ODATA`_ $top query option to select the first n items of the return set for return (default = 50, maximum = 100).
       -  100  
    *  -  $skiptoken
       -  An `ODATA`_ $skiptoken query option to skip over items until the specified item is reached and return the rest.
       -  Paged=TRUE&p_ID=100       

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/get-tickets.png
   :alt: Get tickets example

Create a ticket
----------------------------------

Creates new ticket and returns created ticket.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Ticket
       -  Created ticket object
       -  .. code-block:: json

            {
			  "subject": "Printer issues",
			  "requester": {
			    "id": 10,
			    "title": "John Davis",
			    "email": "j.davis@example.com",
			    "spUserId": null,
			    "role": "End-User",
			    "emailAlternate": null,
			    "customFields": {}
			  },
			  "assignedTo": null,
			  "status": "New",
			  "category": "Problem",
			  "priority": "High",
			  "dueDate": null,
			  "created": "2018-04-28T08:54:57Z",
			  "resolutionDate": "0001-01-01T00:00:00",
			  "cc": [
			    {
			      "id": 8,
			      "title": "Mary Smith",
			      "email": "m.smith@example.com",
			      "spUserId": null,
			      "role": "End-User",
			      "emailAlternate": null,
			      "customFields": {}
			    },
			    {
			      "id": 9,
			      "title": "Jane Jones",
			      "email": "j.jones@example.com",
			      "spUserId": null,
			      "role": "End-User",
			      "emailAlternate": null,
			      "customFields": {}
			    }
			  ],
			  "tags": [
			    {
			      "title": "Printers",
			      "id": 1,
			      "customFields": {}
			    }
			  ],
			  "attachments": null,
			  "id": 17,
			  "customFields": {}
			}                

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Ticket
       -  Ticket object to create
       -  .. code-block:: json

			{
			  "subject": "Printer issues",
			  "body": "My printer is not working, please help ASAP.",
			  "requesterEmail": "j.davis@example.com",
			  "category": "Problem",
			  "priority": "High",
			  "ccEmails": [
			    "m.smith@example.com", "j.jones@example.com"
			  ],
			  "tagTitles": [
			    "Printers"
			  ]
			}

.. rubric:: Example


.. image:: ../../_static/img/flow-actions/create-ticket.png
   :alt: Create ticket example

Delete a ticket
----------------------------

Deletes a ticket by ID.

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  ID
       -  Ticket ID to delete
       -  1          

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/delete-ticket.png
   :alt: Delete a ticket example

Get a single ticket
----------------------------

Gets a single ticket by ID and returns it.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Ticket
       -  Ticket object.
       -   .. code-block:: json

            {
			  "subject": "Printer issues",
			  "requester": {
			    "id": 10,
			    "title": "John Davis",
			    "email": "j.davis@example.com",
			    "spUserId": null,
			    "role": "End-User",
			    "emailAlternate": null,
			    "customFields": {}
			  },
			  "assignedTo": null,
			  "status": "New",
			  "category": "Problem",
			  "priority": "High",
			  "dueDate": null,
			  "created": "2018-04-28T08:54:57Z",
			  "resolutionDate": "0001-01-01T00:00:00",
			  "cc": [
			    {
			      "id": 8,
			      "title": "Mary Smith",
			      "email": "m.smith@example.com",
			      "spUserId": null,
			      "role": "End-User",
			      "emailAlternate": null,
			      "customFields": {}
			    },
			    {
			      "id": 9,
			      "title": "Jane Jones",
			      "email": "j.jones@example.com",
			      "spUserId": null,
			      "role": "End-User",
			      "emailAlternate": null,
			      "customFields": {}
			    }
			  ],
			  "tags": [
			    {
			      "title": "Printers",
			      "id": 1,
			      "customFields": {}
			    }
			  ],
			  "attachments": null,
			  "id": 17,
			  "customFields": {}
			}               

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  ID
       -  Ticket ID
       -  15  
    *  -  includeAttachments
       -  By default result will not contain any attachments. To load ticket attachments you must set parameter "includeAttachments" to Yes.
       -  Yes
    *  -  $select
       -  An `ODATA`_ $select query option to specify which fields to return for a list item. You can use * to return all available fields.
       -  SupportChannel,HelpDeskMailbox,Metadata/IsRead
    *  -  $expand
       -  An `ODATA`_ $expand query option to specify that the request returns the values of lookups.
       -  Metadata

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/get-ticket.png
   :alt: Get ticket by ID example

Update a ticket
----------------------------

Gets a ticket by ID and updates it. Returns updated ticket.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Ticket
       -  Updated ticket object.
       -   .. code-block:: json

            {
			  "subject": "Printer issues",
			  "requester": {
			    "id": 10,
			    "title": "John Davis",
			    "email": "j.davis@example.com",
			    "spUserId": null,
			    "role": "End-User",
			    "emailAlternate": null,
			    "customFields": {}
			  },
			  "assignedTo": null,
			  "status": "New",
			  "category": "Problem",
			  "priority": "High",
			  "dueDate": null,
			  "created": "2018-04-28T08:54:57Z",
			  "resolutionDate": "0001-01-01T00:00:00",
			  "cc": [
			    {
			      "id": 8,
			      "title": "Mary Smith",
			      "email": "m.smith@example.com",
			      "spUserId": null,
			      "role": "End-User",
			      "emailAlternate": null,
			      "customFields": {}
			    },
			    {
			      "id": 9,
			      "title": "Jane Jones",
			      "email": "j.jones@example.com",
			      "spUserId": null,
			      "role": "End-User",
			      "emailAlternate": null,
			      "customFields": {}
			    }
			  ],
			  "tags": [
			    {
			      "title": "Printers",
			      "id": 1,
			      "customFields": {}
			    }
			  ],
			  "attachments": null,
			  "id": 17,
			  "customFields": {}
			}               

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  ID
       -  Ticket ID
       -  15
    *  -  Ticket
       -  Ticket object
       -  .. code-block:: json

			{			 
			  "category": "Problem",
			  "priority": "High",
			  "ccEmails": [
			    "m.smith@example.com", "j.jones@example.com"
			  ],
			  "tagTitles": [
			    "Printers"
			  ]
			}
    

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/update-ticket.png
   :alt: Update a ticket example

Get all comments for a ticket
----------------------------

Gets all comments for a ticket with specified Id.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Comments
       -  Array of comment objects
       -  .. code-block:: json
            [
                {
                    "body": "This is the first comment. Feel free to delete this sample ticket.",
                    "created": "2018-04-27T13:10:05Z",
                    "fromEmail": "mymail@mysite.com",
                    "fromName": "End-User Sample",
                    "messageId": null,
                    "id": 1,
                    "customFields": {}
                },
                {
                    "body": "This is a private comment (no notifications sent to requester) that you added. You also changed the ticket priority to High. You can view a ticket's complete history by selecting the History link in the ticket.",
                    "created": "2018-04-27T13:10:06Z",
                    "fromEmail": null,
                    "fromName": "Anna Zabolotskaya",
                    "messageId": null,
                    "id": 2,
                    "customFields": {}
                }
            ]

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  ticketId
       -  Ticket ID
       -  1
    *  -  $select
       -  An `ODATA`_ $select query option to specify which fields to return for a list item. You can use * to return all available fields.
       -  CommentType,From/Role
    *  -  $expand
       -  An `ODATA`_ $expand query option to specify that the request returns the values of lookups.
       -  From
    *  -  $filter
       -  An `ODATA`_ $filter query option to restrict the entries returned
       -  CommentType eq 'Reply'  
    *  -  $orderBy
       -  An `ODATA`_ $orderBy query option for specifying the order of entries.
       -  ID desc

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/get-comments.png
   :alt: Get comments example

Create a comment
----------------------------

Creates new comment for a ticket with specified Id and returns it.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Comment
       -  Created comment object
       -  .. code-block:: json
            {
                "body": "The issue is still not resolved!",
                "created": "2018-04-28T09:48:07Z",
                "fromEmail": "j.jones@example.com",
                "fromName": "James Jones",
                "messageId": null,
                "id": 25
            }

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  ticketId
       -  Ticket ID
       -  1
    *  -  comment
       -  comment object to create
       -  .. code-block:: json

            {
                "body": "The issue is still not resolved!",
                "fromEmail": "j.jones@example.com"
            }

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/create-comment.png
   :alt: Create comment example

Get a single comment
--------------------

Gets a comment by Id and returns it.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Comment
       -  Comment object
       -  .. code-block:: json

                {
                    "body": "This is the first comment. Feel free to delete this sample ticket.",
                    "created": "2018-04-27T13:10:05Z",
                    "fromEmail": "mymail@mysite.com",
                    "fromName": "End-User Sample",
                    "messageId": null,
                    "id": 1,
                    "customFields": {}
                }

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  id
       -  Comment ID
       -  1
    *  -  $select
       -  An `ODATA`_ $select query option to specify which fields to return for a list item. You can use * to return all available fields.
       -  CommentType,From/Role
    *  -  $expand
       -  An `ODATA`_ $expand query option to specify that the request returns the values of lookups.
       -  From

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/get-comment.png
   :alt: Get comments example

.. _ODATA: https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/use-odata-query-operations-in-sharepoint-rest-requests   