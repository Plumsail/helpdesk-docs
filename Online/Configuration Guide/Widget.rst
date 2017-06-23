Widget
######

.. admonition:: Known issues
	:class: warning

	The latest version of Google Chrome browser doesn't support embedding scripts with Script Editor Web Part.
	Please use different browsers like Microsoft Edge or Mozilla Firefox.

HelpDesk Widget is a web part app for requesters. This widget can be embedded on your site, so customers can easily submit tickets and review them. Here is 'My tickets' view looks like for end-users:

|WidgetView|

Adding widget to SharePoint site
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Open SharePoint site where you want to place the widget.

Install Plumsail HelpDesk Widget add-in from `SharePoint App store <https://store.office.com/en-us/app.aspx?assetid=WA104380769&sourcecorrid=764978a8-0233-4b42-b2e4-7724d130dcf5&searchapppos=0&ui=en-US&rs=en-US&ad=US&appredirect=false&canaryguid=c737b959d79b439bb20bebb5befabc00&reviewedAssetRating=5&AuthType=1&fromAR=1>`_. Installing of the add-in is required to enable automitic sign-in under current SharePoint user in widget.

Then you need to place widget to specific SharePoint page. Steps to do that are described below.

Navigate to e-mail settings using navbar.

|EmailSettings|

Then click “Widgets” tab.

|WidgetTab|

Here you can create a new widget configuration for your page by choosing 'New item' and edit any existing configurations by clicking 'Edit'. Note that editing of widget configuration is employing to every existing widget with this configuration.

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
