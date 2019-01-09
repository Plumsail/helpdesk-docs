Customize ticket and contact forms
##################################

.. important:: `Forms Designer <https://spform.com/>`_ is included into "Yacht" and "Ocean liner" plans. You have to purchase it separately for "Jet boat" plan.

In order to customize ticket and contact forms you need to install `Forms Designer <https://spform.com/>`_.
It is available for free for HelpDesk customizations.
Forms Designer allows to design SharePoint forms with tabs,
complex tables, and accordions among other UI elements.

Using Forms Designer
-------------------

To start using Forms Designer please `download <https://services.spform.com/fd/app/setup.exe>`_ a desktop app and run the installation file on your computer. To connect to HelpDesk please run the app and enter your login details. Once it's connected to HelpDesk please choose a list you want to work with:

|RunningFormsDesigner|

You can find more information on how to use Forms Designer in `the
documentation`_.

.. contents:: Table of contents
   :local:
   :depth: 1

Create custom forms
-------------------

In order to customize a form with Forms Designer navigate to the list
the form is based on and select List or Library tab in the ribbon. There
you will find a new button called “Design Form” under the “Customize
List” section:

|HelpDeskFDRibbon|

Clicking the button will load Forms Designer where you can edit your
form in a simple drag-and-drop fashion:

|FormsDesigner|

.. _forms backups:

Restore default forms
---------------------

You can easily rollback any changes applied to the form and return to the default form. 
Default form layouts you can find in ``<your HelpDesk site>/HD/FormsBackups/`` folder.

|FormsBackupsFolder|

All layouts are splitted by three folders:

Tickets
	Contains backups of the tickets forms.

Contacts
	Contains backups of the contacts forms.

TicketStatuses
	Contains backups of the ticket statuses forms.

|TicketFormsBackups|

For example, to restore ticket edit form you need to do following steps:

1. Download file from ``<your HelpDesk site>/HD/FormsBackups/Tickets/Item_edit.xfds``.
2. Navigate to any tickets list view (for example click on "Home" button on navbar).
3. Click on "Design Forms" button in the ribbon.
4. Select "Edit Form" in Forms Designer.
5. Click on "Import" button.
6. Select downloaded file "Item_edit.xfds".
7. Save the form. 

.. _Forms Designer: https://store.office.com/plumsail-forms-designer-WA104231938.aspx?assetid=WA104231938
.. _the documentation: http://spform.com/documentation

.. |HelpDeskFDRibbon| image:: ../_static/img/helpdeskfdribbon.png
   :alt: Forms Designer Ribbon
.. |FormsDesigner| image:: ../_static/img/formsdesigner.png
   :alt: Forms Designer
.. |FormsBackupsFolder| image:: ../_static/img/forms-backups-0.png
   :alt: Forms Backups Folder
.. |TicketFormsBackups| image:: ../_static/img/forms-backups-1.png
   :alt: Forms Backups Folder
.. |RunningFormsDesigner| image:: ../_static/img/Forms-Designer-in-HD.jpg
   :alt: Running Forms Designer
