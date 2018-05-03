How to submit tickets from an online form to SharePoint HelpDesk with the help of Microsoft Flow or Azure Logic Apps connector
##############################################################

One of a simple ways to improve communication with clients or within a company is to create a custom form that can be used to send a feedback, to report a problem, to request assistance or just to get some information in general.

In this example, we will design a form for customers for submitting messages and use Plumsail HelpDesk connector in Microsoft Flow to create a new ticket in Plumsail Helpdesk for Office 365.

This is an example of the form that will create a ticket:

|FormPreview|


Design a form
~~~~~~~~~~~~~

First, design a form. We will do it with help of Plumsail Forms, but you can use any other forms solution that can submit data to Microsoft Flow.

Think about what information might need to be specified: a subject for the ticket, request’s category, customer’s location, operation system, etc.

Don’t forget to include the Submit button, so the form can be actually submitted. Flow only starts operating once the form is submitted.

This short article gives a better understanding of how to work with Plumsail Forms.

Here’s a simple form designed to receive messages from customers:

|SimpleForm|

Once you design and save the form, place it on a page where you would like the form to appear. You may add it to your public website or a page in SharePoint Online in Office 365.


Configure the Flow — First steps
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Here, I will guide you step by step through creating the flow. You also will find a screenshot of the complete flow at the end of the article. 

First, open Microsoft Flow, go to My Flows, click Create from blank to create a new Flow, search for and add Plumsail Forms — Form is submitted. 

Next, you need to fill in Form ID. You can find the Form Id in the Plumsail Forms if you click the Flow button. Alternatively, you can always check it in your Plumsail account.

|FormIsSubmitted|

---------

By default, `Plumsail HelpDesk`_ doesn’t assign unique permissions to each ticket. HelpDesk site can be used by anyone to create tickets or reply to them. If you want to change this behavior, you should restrict access to help desk site for non-agents and use HelpDesk widget as an interface for requesters instead. It displays only tickets that are created by the current user.

Please review `this instruction`_ to understand how to place the widget on a page.

Pay attention to `this step`_ of installing add-in from SharePoint app store. It is required to allow the widget to automatically detect the current user (single sign-on). If you don't install it, the widget will ask requesters for login and password.


Restricting access to the HelpDesk site
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The only thing we need to do is to restrict access to the Plumsail HelpDesk site and allow access to agents only.

After following this instruction you should have a separate `Plumsail HelpDesk`_ site that is shared with your agents and another site with a page where requesters can see or create their own tickets. If you didn't install it yet, `download it`_ and follow the installation instruction for your version of SharePoint in the documentation. It is quite easy to get started.


.. |FormPreview| image:: ../_static/img/form-preview.png
   :alt: Plumsail form to create a ticket

.. |SimpleForm| image:: ../_static/img/form-in-form-designer.png
   :alt: Plumsail form to create a ticket

.. |FormIsSubmitted| image:: ../_static/img/form-is-submitted.png
   :alt: Plumsail form to create a ticket


.. _Plumsail HelpDesk: https://plumsail.com/sharepoint-helpdesk/

.. _this instruction: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Adding%20widget%20to%20SharePoint%20site.html

.. _this step: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Adding%20widget%20to%20SharePoint%20site.html#enable-automatic-sign-in-for-a-widget

.. _download it: https://plumsail.com/sharepoint-helpdesk/download/