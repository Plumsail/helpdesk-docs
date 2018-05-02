Rich REST API
=======================================

This tutorial shows how to use Plumsail HelpDesk API. There are just a few steps to get started:

1. :ref:`create-api-key`
2. :ref:`review-api-reference`
3. :ref:`use-own-language`

.. _create-api-key:

Create an API key
-----------------

HelpDesk REST API uses API keys for authentification. To generate API key just follow the steps described in `this topic <get-api-key.html>`_

.. _review-api-reference:

Review reference for API
------------------------

You can find links to references for all Actions APIs on `this page <https://helpdesk-services.plumsail.com/_api/swagger>`_.

.. _use-own-language:

Use API from your programming language
---------------------------------------------

Our API is REST based. Thus, you can use any programming language that is able to execute web requests. For example, you would use C#, PowerShell, node.js, Python, PHP.

There are a lot of ready to use helper REST API clients for those languages. Here are just a few of them:

- `RestSharp <http://restsharp.org/>`_ for C#
- `Invoke-RestMethod <https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-5.1>`_ cmdlets for PowerShell
- `request <https://www.npmjs.com/package/request>`_ - Simplified HTTP client for node.js
- `Requests: HTTP for Humans <http://docs.python-requests.org>`_ for Python
- `Guzzle <http://guzzle.readthedocs.io>`_ for PHP

Usage examples
--------------

Here you can see a couple of examples of using HelpDesk REST API.

1. :ref:`get-tickets`
2. :ref:`create-ticket`
3. :ref:`delete-ticket`
4. :ref:`update-ticket`

.. _get-tickets:

Get tickets
~~~~~~~~~~~~~~~~~~~~~~

This is an example of a raw request to get tickets:

::

    GET https://helpdesk-services.plumsail.com/_api/v4/Tickets?includeAttachments=true&$select=SupportChannel&$filter=SupportChannel%20eq%20'API'&$orderBy=ID%20desc&$top=100 HTTP/1.1
    Accept: application/json
    X-HD-ApiKey: YOUR_API_KEY
    Host: helpdesk-services.plumsail.com

And this is cURL representation for it:

::

    curl -X GET --header 'Accept: application/json' --header 'X-HD-ApiKey: YOUR_API_KEY' 'https://helpdesk-services.plumsail.com/_api/v4/Tickets?includeAttachments=true&$select=SupportChannel&$filter=SupportChannel%20eq%20'API'&$orderBy=ID%20desc&$top=100'

.. _create-ticket:

Create a ticket
~~~~~~~~~~~~~~~~~~~~~~

This is an example of a raw request to create a ticket:

::

    POST https://helpdesk-services.plumsail.com/_api/v4/Tickets HTTP/1.1
    Accept: application/json
    X-HD-ApiKey: YOUR_API_KEY
    Content-Type: application/json

    {
    "subject": "Printer Issues",
    "body": "My printer is not working. Please help. ASAP.",
    "requesterEmail": "m.cane@emaple,com",
    "priority": "High",
    "tagTitles": [
        "Printers"
    ],
    "attachments": [
        {
        "Name": "error.txt",
        "Content": "BASE64_FILE_CONTENT"
        }
    ],
    "customFields": {}
    }

And this is cURL representation for it:

::

    curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' --header 'X-HD-ApiKey: YOUR_API_KEY' -d '{ \ 
    "subject": "Printer Issues", \ 
    "body": "My printer is not working. Please help. ASAP.", \ 
    "requesterEmail": "m.cane%40emaple,com", \ 
    "priority": "High", \ 
    "tagTitles": [ \ 
        "Printers" \ 
    ], \ 
    "attachments": [ \ 
        { \ 
        "Name": "error.txt", \ 
        "Content": "BASE64_FILE_CONTENT" \ 
        } \ 
    ], \ 
    "customFields": {} \ 
    }' 'https://helpdesk-services.plumsail.com/_api/v4/Tickets'

.. _delete-ticket:

Delete a ticket
~~~~~~~~~~~~~~~~~~~~~~

This is an example of a raw request to delete a ticket:

::

    DELETE https://helpdesk-services.plumsail.com/_api/v4/Tickets/1 HTTP/1.1
    X-HD-ApiKey: YOUR_API_KEY

And this is cURL representation for it:

::

    curl -X DELETE --header 'X-HD-ApiKey: YOUR_API_KEY' 'https://helpdesk-services.plumsail.com/_api/v4/Tickets/1'

.. _update-ticket:

Update a ticket
~~~~~~~~~~~~~~~~~~~~~~

This is an example of a raw request to update a ticket:

::

    PUT https://helpdesk-services.plumsail.com/_api/v4/Tickets/18 HTTP/1.1
    X-HD-ApiKey: YOUR_API_KEY
    Accept: application/json
    Content-Type: application/json

    {
    "assignedToEmail": "j.davis@example.com",
    "status": "In progress",
    "category": "Problem",
    "priority": "Normal",
    "dueDate": "2018-05-07",
    "ccEmails": [
        "j.davis@example.com", "m.smith@example.com"
    ]
    }

And this is cURL representation for it:

::

    curl -X PUT --header 'Content-Type: application/json' --header 'Accept: application/json' --header 'X-HD-ApiKey: YOUR_API_KEY' -d '{ \ 
    "assignedToEmail": "j.davis@example.com", \ 
    "status": "In progress", \ 
    "category": "Problem", \ 
    "priority": "Normal", \ 
    "dueDate": "2018-05-07", \ 
    "ccEmails": [ \ 
        "j.davis%40example.com", "m.smith%40example.com" \ 
    ] \ 
    }' 'https://helpdesk-services.plumsail.com/_api/v4/Tickets/18'