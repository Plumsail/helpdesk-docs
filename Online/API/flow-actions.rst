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
       -  Array of tickets. All custom fields listed in $select parameter are returned in the customFields object. 
       -  Example of ticket in JSON format:

          .. code-block:: json
        
            {
                "subject": "Site issues",
                "requester": { ... },
                "assignedTo": { ... },    
                "status": "In progress",
                "category": "Question",
                "priority": "High",
                "dueDate": "2018-04-27",
                "created": "2018-04-27,
                "resolutionDate": "",
                "cc": [],
                "tags": [],
                "attachments": null,
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
       -  Created ticket. All custom fields listed in $select parameter are returned in the customFields object. 
       -  Example of ticket in JSON format:

          .. code-block:: json

            {
                "subject": "Site issues",
                "requester": { ... },
                "assignedTo": { ... },    
                "status": "In progress",
                "category": "Question",
                "priority": "High",
                "dueDate": "2018-04-27",
                "created": "2018-04-27,
                "resolutionDate": "",
                "cc": [],
                "tags": [],
                "attachments": null,
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
    *  -  Ticket Subject
       -  Subject
       -  Printer issues
    *  -  Ticket Body
       -  Body
       -  My printer is not working, please help ASAP.
    *  -  Ticket Requester Email
       -  Requester email
       -  j.davis@example.com
    *  -  Ticket Assignee Email or Sharepoint Group
       -  Assignee email or the name of SharePoint group to which the ticket will be assigned to.
       -  j.davis@example.com or IT support
    *  -  Ticket Status
       -  Status name
       -  In progress
    *  -  Ticket Category
       -  Category name
       -  Problem
    *  -  Ticket Priority
       -  Priority name
       -  High
    *  -  Ticket DueDate
       -  DueDate
       -  01.05.2018
    *  -  Ticket Cc Emails
       -  Array if Cc emails
       -  ["j.davis@example.com", "m.smith@example.com"]
    *  -  Ticket Tags tagTitles
       -  Array of ticket tags, new tags will be created in Tags list automatically.
       -  ["Printers", "MS Windows"]
    *  -  Ticket Attachments
       -  Array of object containing File Names and File Contents.
       -  File Name: screenshot.png

          File Content: You can extract file content from other connectors like:  

            - SharePoint
            - Salesforce
            - Box
            - OneDrive
            - Google Drive
            - Dropbox
            - SFTP
            - File System          

          `List of Microsoft Flow connectors <https://flow.microsoft.com/en-us/connectors/>`_      
    *  -  Ticket Support Channel
       -  Support channel name, if no value is provided, it will be set to API
       -  Company site
    *  -  Ticket Custom Fields
       -  JSON object with custom field values to be set.
       -  .. code-block:: json

            {
                "Location": "Europe",
                "OperatingSystem": "MS Windows 10"
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
       -  Requested ticket. All custom fields listed in $select parameter are returned in the customFields object. 
       -  Example of ticket in JSON format:

          .. code-block:: json

            {
                "subject": "Site issues",
                "requester": { ... },
                "assignedTo": { ... },    
                "status": "In progress",
                "category": "Question",
                "priority": "High",
                "dueDate": "2018-04-27",
                "created": "2018-04-27,
                "resolutionDate": "",
                "cc": [],
                "tags": [],
                "attachments": null,
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
       -  Updated ticket.
       -  Example of ticket in JSON format:

          .. code-block:: json

            {
                "subject": "Site issues",
                "requester": { ... },
                "assignedTo": { ... },    
                "status": "In progress",
                "category": "Question",
                "priority": "High",
                "dueDate": "2018-04-27",
                "created": "2018-04-27,
                "resolutionDate": "",
                "cc": [],
                "tags": [],
                "attachments": null,
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
    *  -  Ticket Subject
       -  Subject
       -  Printer issues
    *  -  Ticket Body
       -  Body
       -  My printer is not working, please help ASAP.
    *  -  Ticket Requester Email
       -  Requester email
       -  j.davis@example.com
    *  -  Ticket Assignee Email or Sharepoint Group
       -  Assignee email or the name of SharePoint group to which the ticket will be assigned to.
       -  j.davis@example.com or IT support
    *  -  Ticket Status
       -  Status name
       -  In progress
    *  -  Ticket Category
       -  Category name
       -  Problem
    *  -  Ticket Priority
       -  Priority name
       -  High
    *  -  Ticket DueDate
       -  DueDate
       -  01.05.2018
    *  -  Ticket Cc Emails
       -  Array if Cc emails
       -  ["j.davis@example.com", "m.smith@example.com"]
    *  -  Ticket Tags tagTitles
       -  Array of ticket tags, new tags will be created in Tags list automatically.
       -  ["Printers", "MS Windows"]
    *  -  Ticket Attachments
       -  Array of object containing File Names and File Contents.
       -  File Name: screenshot.png

          File Content: You can extract file content from other connectors like:  

            - SharePoint
            - Salesforce
            - Box
            - OneDrive
            - Google Drive
            - Dropbox
            - SFTP
            - File System          

          `List of Microsoft Flow connectors <https://flow.microsoft.com/en-us/connectors/>`_      
    *  -  Ticket Support Channel
       -  Support channel name, if no value is provided, it will be set to API
       -  Company site
    *  -  Ticket Custom Fields
       -  JSON object with custom field values to be set.
       -  .. code-block:: json

            {
                "Location": "Europe",
                "OperatingSystem": "MS Windows 10"
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
       -  Array of comments. All custom fields listed in $select parameter are returned in the customFields object. 
       -  Example of comment in JSON format:

          .. code-block:: json

            {
                "body": "The issue is still not resolved!",
                "created": "2018-04-28T09:48:07Z",
                "fromEmail": "j.jones@example.com",
                "fromName": "James Jones",
                "messageId": null,
                "id": 25,
                "customFields": {}
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
       -  Created comment
       -  Example of comment in JSON format:

          .. code-block:: json

            {
                "body": "The issue is still not resolved!",
                "created": "2018-04-28T09:48:07Z",
                "fromEmail": "j.jones@example.com",
                "fromName": "James Jones",
                "messageId": null,
                "id": 25,
                "customFields": {}
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
    *  -  Comment Body
       -  Body of the comment
       -  The issue is still not resolved!
    *  -  Comment Author Email
       -  Email of the author of the comment
       -  j.jones@example.com
    *  -  Attachments
       -  Array of object containing File Names and File Contents.
       -  File Name: screenshot.png

          File Content: You can extract file content from other connectors like:  

            - SharePoint
            - Salesforce
            - Box
            - OneDrive
            - Google Drive
            - Dropbox
            - SFTP
            - File System          

          `List of Microsoft Flow connectors <https://flow.microsoft.com/en-us/connectors/>`_  
    *  -  Comment MessageId
       -  Message-ID of email message, if comment is being created from email
       -  <SN2PR0501MB10559C65E048C190F1B401F9AF8E0@SN2PR0501MB1055.namprd05.prod.outlook.com>
    *  -  Comment Custom Fields
       -  JSON object with custom field values to be set for comment.
       -  .. code-block:: json

            {
                "Location": "Europe",
                "OperatingSystem": "MS Windows 10"
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
       -  Comment
       -  Example of comment in JSON format:

          .. code-block:: json

            {
                "body": "The issue is still not resolved!",
                "created": "2018-04-28T09:48:07Z",
                "fromEmail": "j.jones@example.com",
                "fromName": "James Jones",
                "messageId": null,
                "id": 25,
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

Get contacts
----------------------------------

Get contacts. By default this actions returns first 50 contacts.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Contacts
       -  Array of contacts. All custom fields listed in $select parameter are returned in the customFields object. 
       -  Example of contact in JSON format:

          .. code-block:: json
        
            {
                "title": "Mary Smith",
                "email": "m.smith@example.com",
                "spUserId": 0,
                "role": "End-User",
                "emailAlternate": "m.smith@google.com",
                "id": 20,
                "customFields": {}
            } 
     		

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  $select
       -  An `ODATA`_ $select query option to specify which fields to return for a list item. You can use * to return all available fields.
       -  PhoneNumber,IsValidated,Organization/Title
    *  -  $expand
       -  An `ODATA`_ $expand query option to specify that the request returns the values of lookups.
       -  Organization
    *  -  $filter
       -  An `ODATA`_ $filter query option to restrict the entries returned
       -  Role eq 'Agent'  
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

.. image:: ../../_static/img/flow-actions/get-contacts.png
   :alt: Get contacts example

Create a contact
----------------------------------

Creates new contact and returns it.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Contact
       -  All custom fields listed in $select parameter are returned in the customFields object. 
       -  Example of contact in JSON format:

          .. code-block:: json
        
            {
                "title": "Mary Smith",
                "email": "m.smith@example.com",
                "spUserId": 0,
                "role": "End-User",
                "emailAlternate": "m.smith@google.com",
                "id": 20,
                "customFields": {}
            } 
     		

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  updateIfExists
       -  If contact with specified email already exists and updateIfExists parameter is set to Yes, contact information will be updated
       -  Yes
    *  -  Contact Name
       -  Full name of the contact
       -  Mary Cane
    *  -  Contact Email
       -  Email of the contact
       -  m.cane@example.com
    *  -  Contact SPUserId
       -  You can provide SPUser ID instead of contact email, if you want to create Agent or Member
       -  15
    *  -  Contact Role
       -  Role of the contact  in HelpDesk
       -  En-User, Member or Agent
    *  -  Contact Alterate Email
       -  Alterate email address for the contact
       -  m.cane@outlook.com
    *  -  Contact Custom Fields
       -  JSON object with custom field values to be set.
       -  .. code-block:: json

            {
                "Location": "USA",
                "PhoneNumber": "(123)123-1234"
            }  

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/create-contact.png
   :alt: Create contact example

Get a single contact by Email
----------------------------------

Gets a contact by email and returs it.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Requested contact
       -  All custom fields listed in $select parameter are returned in the customFields object. 
       -  Example of contact in JSON format:

          .. code-block:: json
        
            {
                "title": "Mary Smith",
                "email": "m.smith@example.com",
                "spUserId": 0,
                "role": "End-User",
                "emailAlternate": "m.smith@google.com",
                "id": 20,
                "customFields": {}
            } 
     		

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  email
       -  Contact email
       -  m.cane@example.com
    *  -  $select
       -  An `ODATA`_ $select query option to specify which fields to return for a list item. You can use * to return all available fields.
       -  PhoneNumber,IsValidated,Organization/Title
    *  -  $expand
       -  An `ODATA`_ $expand query option to specify that the request returns the values of lookups.
       -  Organization

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/get-contact-by-email.png
   :alt: Get contact by email example

Update a contact by Email
----------------------------------

Finds a contact by email and updates it. Returns updated contact.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Contact
       -  Updated contact 
       -  Example of contact in JSON format:

          .. code-block:: json
        
            {
                "title": "Mary Smith",
                "email": "m.smith@example.com",
                "spUserId": 0,
                "role": "End-User",
                "emailAlternate": "m.smith@google.com",
                "id": 20,
                "customFields": {}
            } 
     		

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Contact Email
       -  Email of the contact
       -  m.cane@example.com
    *  -  Contact Name
       -  Full name of the contact
       -  Mary Cane
    *  -  Contact SPUserId
       -  You can provide SPUser ID instead of contact email, if you want to create Agent or Member
       -  15
    *  -  Contact Role
       -  Role of the contact  in HelpDesk
       -  En-User, Member or Agent
    *  -  Contact Alterate Email
       -  Alterate email address for the contact
       -  m.cane@outlook.com
    *  -  Contact Custom Fields
       -  JSON object with custom field values to be set.
       -  .. code-block:: json

            {
                "Location": "USA",
                "PhoneNumber": "(123)123-1234"
            }  

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/update-contact-by-email.png
   :alt: Update contact by email example

Delete a contact
----------------------------

Deletes a contact by ID.

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  id
       -  Contact ID to delete
       -  1          

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/delete-contact.png
   :alt: Delete a contact example

Get a single contact by ID
----------------------------------

Gets a contact by ID and returs it.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Requested contact
       -  All custom fields listed in $select parameter are returned in the customFields object. 
       -  Example of contact in JSON format:

          .. code-block:: json
        
            {
                "title": "Mary Smith",
                "email": "m.smith@example.com",
                "spUserId": 0,
                "role": "End-User",
                "emailAlternate": "m.smith@google.com",
                "id": 20,
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
       -  Contact ID
       -  20
    *  -  $select
       -  An `ODATA`_ $select query option to specify which fields to return for a list item. You can use * to return all available fields.
       -  PhoneNumber,IsValidated,Organization/Title
    *  -  $expand
       -  An `ODATA`_ $expand query option to specify that the request returns the values of lookups.
       -  Organization

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/get-contact-by-id.png
   :alt: Get contact by ID example

Update a contact by ID
----------------------------------

Finds a contact by ID and updates it. Returns updated contact.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Contact
       -  Updated contact 
       -  Example of contact in JSON format:

          .. code-block:: json
        
            {
                "title": "Mary Smith",
                "email": "m.smith@example.com",
                "spUserId": 0,
                "role": "End-User",
                "emailAlternate": "m.smith@google.com",
                "id": 20,
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
       -  Contact ID
       -  20
    *  -  Contact Name
       -  Full name of the contact
       -  Mary Cane
    *  -  Contact Email
       -  Email of the contact
       -  m.cane@example.com
    *  -  Contact SPUserId
       -  You can provide SPUser ID instead of contact email, if you want to create Agent or Member
       -  15
    *  -  Contact Role
       -  Role of the contact  in HelpDesk
       -  En-User, Member or Agent
    *  -  Contact Alterate Email
       -  Alterate email address for the contact
       -  m.cane@outlook.com
    *  -  Contact Custom Fields
       -  JSON object with custom field values to be set.
       -  .. code-block:: json

            {
                "Location": "USA",
                "PhoneNumber": "(123)123-1234"
            }  

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/update-contact-by-id.png
   :alt: Update contact by email example

.. _ODATA: https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/use-odata-query-operations-in-sharepoint-rest-requests   