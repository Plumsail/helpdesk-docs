Power Automate (Microsoft Flow) Actions
======================

This connector helps you to manipulate data in your HelpDesk with the help of Power Automate (Microsoft Flow). Before starting, ensure that you `added Plumsail HelpDesk connector to Power Automate (Microsoft Flow) <https://plumsail.com/docs/help-desk-o365/v1.x/API/ms-flow.html>`_.

.. contents:: List of actions in this connector
   :local:
   :depth: 1

Get tickets
----------------------------------

Get tickets. By default this action returns first 50 tickets.

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
       -  #. *Manual* adding of attachments. Specify a file name and pass its content from another action. To add an attachment item, click an accordant button. Check the "Ticket Attachments" section of the action on the `screenshot <./flow-actions.html#screenshot-createticket>`_ below.
          #. *Dynamical* adding of attachments. If the number of attachments varies and depends on output of other actions, then use the approach described in this `article <../How%20To/Submit%20tickets%20from%20an%20online%20form%20to%20SharePoint%20help%20desk%20with%20the%20help%20of%20Power%20Automate%20(Microsoft%20Flow)%20or%20Azure%20Logic%20Apps%20connector.html#handling-attachments>`_.
    *  -  Ticket Support Channel
       -  Support channel name, if no value is provided, it will be set to API
       -  Company site
    *  -  Ticket Custom Fields
       -  JSON object with custom field values to be set. There is a specific way to set a multichoice field (check the "Languages" property).
       -  .. code-block:: json

            {
                "Location": "Europe",
                "OperatingSystem": "MS Windows 10",
                "Languages": {
                    "results": ["English", "French"]
                }
            }

.. rubric:: Example

.. _screenshot-createticket:

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
    *  -  Ticket Id
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
                "attachments": ["error.png"],
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
    *  -  Ticket Id
       -  Ticket identifier
       -  15  
    *  -  $select
       -  An `ODATA`_ $select query option to specify which fields to return for a list item. You can use * to return all available fields.
       -  SupportChannel,HelpDeskMailbox,Metadata/IsRead
    *  -  $expand
       -  An `ODATA`_ $expand query option to specify that the request returns the values of lookups.
       -  Metadata

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/get-ticket.png
   :alt: Get ticket by ID example

Download attachment
----------------------------

Returns attachment file for specific ticket by its name

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30

    *  -  Parameter
       -  Description       
    *  -  Attachment
       -  Requested attachment file 
       
.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Ticket Id
       -  Ticket identifier
       -  15  
    *  -  Attachment Filename
       -  Attachment Filename
       -  error.png
    
.. rubric:: Example

.. image:: ../../_static/img/flow-actions/download-attachment.png
   :alt: Download attachment example

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
    *  -  Ticket Id
       -  Ticket identifier
       -  15  
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

          `List of Power Automate (Microsoft Flow) connectors <https://flow.microsoft.com/en-us/connectors/>`_      
    *  -  Ticket Support Channel
       -  Support channel name, if no value is provided, it will be set to API
       -  Company site
    *  -  Ticket Custom Fields
       -  JSON object with custom field values to be set. There is a specific way to set a multichoice field (check the "Languages" property).
       -  .. code-block:: json

            {
                "Location": "Europe",
                "OperatingSystem": "MS Windows 10",
                "Languages": {
                    "results": ["English", "French"]
                }
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
    *  -  Ticket Id
       -  Ticket identifier
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
    *  -  Ticket Id
       -  Ticket identifier
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

          `List of Power Automate (Microsoft Flow) connectors <https://flow.microsoft.com/en-us/connectors/>`_  
    *  -  Comment MessageId
       -  Message-ID of email message, if comment is being created from email
       -  <SN2PR0501MB105.namprd05.prod.outlook.com>
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
    *  -  Ticket Id
       -  Ticket identifier
       -  1
    *  -  Comment Id
       -  Comment identifier
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

Get contacts. By default this action returns first 50 contacts.

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
    *  -  Contact Name
       -  Full name of the contact
       -  Mary Cane
    *  -  Contact Email
       -  HelpDesk checks Email from this field and if it founds a SharePoint user with one, it will create a contact with "Member" role by default. Otherwise, it creates "End-User" one
       -  m.cane@example.com
    *  -  Contact SPUserId
       -  You can provide a SharePoint user ID instead of contact Email, if you want to create Agent or Member. The field is not mandatory
       -  15
    *  -  Contact Role
       -  Role of the contact in HelpDesk. The field is not mandatory
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
            
    *  -  Update if exists
       -  If contact with specified email already exists and "Update if exists" parameter is set to "Yes", contact information will be updated
       -  Yes

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
    *  -  Contact Email
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
    *  -  Contact Id
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
    *  -  Contact Id
       -  Contact identifier
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
    *  -  Contact Id
       -  Contact identifier
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
   :alt: Update contact by ID example

Get organizations
----------------------------------

Get organizations. By default this action returns first 50 organizations.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Organizations
       -  Array of organizations. All custom fields listed in $select parameter are returned in the customFields object. 
       -  Example of Organization in JSON format:

          .. code-block:: json
        
            {
                "title": "Plumsail",
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
    *  -  $select
       -  An `ODATA`_ $select query option to specify which fields to return for a list item. You can use * to return all available fields.
       -  Region,IsPartner,ManagerContact/Email
    *  -  $expand
       -  An `ODATA`_ $expand query option to specify that the request returns the values of lookups.
       -  ManagerContact
    *  -  $filter
       -  An `ODATA`_ $filter query option to restrict the entries returned
       -  Region eq 'Asia'  
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

.. image:: ../../_static/img/flow-actions/get-organizations.png
   :alt: Get organizations example

Create an organization
----------------------------------

Creates new organization and returns it.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Organization
       -  Created organization
       -  Example of Organization in JSON format:

          .. code-block:: json
        
            {
                "title": "Plumsail",
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
    *  -  Organization Title
       -  Title of the organization
       -  Plumsail
    *  -  Organization Custom Fields
       -  JSON object with custom field values to be set.
       -  .. code-block:: json

            {
                "Location": "USA",
                "PhoneNumber": "(123)123-1234"
            }
     

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/create-organization.png
   :alt: Create organization example

Delete an organization
----------------------------------

Deletes an organization by ID.

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Organization Id
       -  Organization identifier
       -  15
     

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/delete-organization.png
   :alt: Delete organization by id example

Get a single organization
----------------------------------

Gets the organization by ID and returns it.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Organization
       -  Found organization
       -  Example of Organization in JSON format:

          .. code-block:: json
        
            {
                "title": "Plumsail",
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
    *  -  Organization Id
       -  Organization identifier
       -  15
    *  -  $select
       -  An `ODATA`_ $select query option to specify which fields to return for a list item. You can use * to return all available fields.
       -  Region,IsPartner,ManagerContact/Email
    *  -  $expand
       -  An `ODATA`_ $expand query option to specify that the request returns the values of lookups.
       -  ManagerContact
     

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/get-organization-by-id.png
   :alt: Get organization by ID example

Update an organization
----------------------------------

Updates an organization and returns it.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Organization
       -  Updated organization
       -  Example of Organization in JSON format:

          .. code-block:: json
        
            {
                "title": "Plumsail",
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
    *  -  Organization Id
       -  Organization identifier
       -  15
    *  -  Organization Title
       -  Title of the organization
       -  New tree inc.
    *  -  Organization Custom Fields
       -  JSON object with custom field values to be set.
       -  .. code-block:: json

            {
                "Location": "USA",
                "PhoneNumber": "(123)123-1234"
            }     

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/update-organization-by-id.png
   :alt: Update organization by id example

Delete an organization by title
----------------------------------

Deletes an organization by title.

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Organization title
       -  Organization Title
       -  New tree inc.
     

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/delete-organization-by-title.png
   :alt: Delete organization by title example

Get a single organization by title
----------------------------------

Gets the organization by Title and returns it.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Organization
       -  Found organization
       -  Example of Organization in JSON format:

          .. code-block:: json
        
            {
                "title": "Plumsail",
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
    *  -  Organization title
       -  Organization Title
       -  New tree inc.
    *  -  $select
       -  An `ODATA`_ $select query option to specify which fields to return for a list item. You can use * to return all available fields.
       -  Region,IsPartner,ManagerContact/Email
    *  -  $expand
       -  An `ODATA`_ $expand query option to specify that the request returns the values of lookups.
       -  ManagerContact
     

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/get-organization-by-title.png
   :alt: Get organization by Title example

Update an organization by title
----------------------------------

Updates an organization and returns it.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Organization
       -  Updated organization
       -  Example of Organization in JSON format:

          .. code-block:: json
        
            {
                "title": "Plumsail",
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
    *  -  Organization Title
       -  Title of the organization
       -  New tree inc.
    *  -  Organization Custom Fields
       -  JSON object with custom field values to be set.
       -  .. code-block:: json

            {
                "Location": "USA",
                "PhoneNumber": "(123)123-1234"
            }     

.. rubric:: Example

.. image:: ../../_static/img/flow-actions/update-organization-by-title.png
   :alt: Update organization by title example

.. _ODATA: https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/use-odata-query-operations-in-sharepoint-rest-requests