Widget
######

HelpDesk Widget is a web part app for requesters. This widget can be embedded to your site, so customers can easily submit tickets and review them. Here is 'My tickets' view looks like for end-users:

|WidgetView|

Adding widget to SharePoint site
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Navigate to e-mail settings using navbar.

|EmailSettings|

Then click “Widgets” tab. 

|WidgetTab|

Here you can create a new widget configuration for your page by choosing 'New item' and edit any existing configurations by clicking 'Edit'. Note that editing of widget configuration is 

|NewWidget|

Provide a title for a widget configuration and choose how many tickets will be displayed on the page. 
If you are creating a widget for external site, you can choose allow or not user's registration. Registrated users have ability to review their tickets.

|WidgetMenu|

After saving this configuration, HTML code will be generated and you need to copy it.

|GenHTML|

Navigate to a page where you'd like to place a widget and click ‘Edit’ on the site ribbon menu. 

|EditPage|

Choose the place where the app will be shown and click ‘Insert’ tab. Here you need to choose ‘Embed code’ option and just paste HTML code which you copied before in the pop-up window. 
Finish with clicking ‘Save’ on the ribbon.

|Finish|

Adding widget to external site
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Adding a widget to an external site is quite similar to adding it to SharePoint site. Just copy an auto-generated HTML code, open editing form of HTML page and add copied code where you'd like to place a widget.

.. |WidgetView| image:: /_static/img/widgetview.png
   :alt: HelpDesk Widget
.. |EmailSettings| image:: /_static/img/settingsicon.png
   :alt: E-mail settings
.. |WidgetTab| image:: /_static/img/tab.png
   :alt: Widget Tab
.. |NewWidget| image:: /_static/img/newitem.png
   :alt: Create a new item
.. |WidgetMenu| image:: /_static/img/newwidget.png
   :alt: Widget settings
.. |GenHTML| image:: /_static/img/gethtml.png
   :alt: Generated HTML code
.. |EditPage| image:: /_static/img/editpage.png
   :alt: Adding a widget to your site
.. |Finish| image:: /_static/img/finish.png
   :alt: Inserting a widget


.. _Install: