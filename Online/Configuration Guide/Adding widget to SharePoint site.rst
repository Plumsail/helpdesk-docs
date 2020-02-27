Adding widget to SharePoint site
################################

.. note::
   Since version 2.1.1 widget web part is included in default HelpDesk installation package. 
   It means you don't need to install it separately as in previous versions and it's available right after HelpDesk installation.

.. contents:: Table of contents
   :local:
   :depth: 1


Creating widget configuration
-----------------------------

Open HelpDesk site and navigate to the **Settings** tab using the left navbar.
Click ont the **Widgets** tab.

|WidgetTab|

Here you can create a new widget configuration for your page by choosing 'New item' and edit any existing configurations by clicking 'Edit'. Note that editing of widget configuration is employing to every existing widget with this configuration.

|NewWidget|

Provide a title for a widget configuration and choose how many tickets will be displayed on the page.

You can customize fields displayed in widget ticket list. To do this you will need to provide a list of comma-separated field names in Display fields section. Note, that you need to use `internal names`_ of the fields. 

If you are creating a widget for external site, you can choose widget language and whether to allow user registration. Registered users have ability to review their tickets.

.. note::
   Display fields customization is available from version 1.4.7.
.. note::
   Display fields are cached for 30 minutes for optimisation purposes. You will need to clear browser cache to apply your changes immediatly.

|WidgetMenu|

After saving, HTML code for external sites and configuration ID for SharePoint will be generated and you need to copy SharePoint Configuration ID.

|GenSPConfigID|

.. _auto-sign-in:

Enable automatic sign-in for a widget
-------------------------------------

Open SharePoint site where you want to place the widget.

Install Plumsail HelpDesk Widget add-in from `SharePoint App store <https://store.office.com/en-us/app.aspx?assetid=WA104380769&sourcecorrid=764978a8-0233-4b42-b2e4-7724d130dcf5&searchapppos=0&ui=en-US&rs=en-US&ad=US&appredirect=false&canaryguid=c737b959d79b439bb20bebb5befabc00&reviewedAssetRating=5&AuthType=1&fromAR=1>`_. Installing of the add-in is required to enable automatic sign-in under current SharePoint user in widget.

Then you need to place widget to specific SharePoint page. Steps to do that are described below.

Adding widget to modern SharePoint page
---------------------------------------

Navigate to a page where you'd like to place a widget.

Pick **Plumsail HelpDesk Widget WebPart** web part from the menu to add it to your page:

|PickWPOnModernPage|

Once you added the web part you need to configure it. Just copy 'Configuration ID for SharePoint' from widget configuration form and paste it to corresponding web part property.

|ConfigureModernWP|

Publish the page. Your HelpDesk widget is ready to use.

|WidgetOnModernPage|

Known issue
-----------

You may encounter the following error trying to `add <Adding%20widget%20to%20SharePoint%20site.html#auto-sign-in>`_ Plumsail HelpDesk Widget to a SharePoint site:

|Widget_Issue|

In this case, click **Find out why** and **Request Approval**.

|Widget_ApprovalRequest|

Enter a reason and request approval.

|Widget_SendRequest|

Then, open `App Catalog <Installation%20of%20HelpDesk%20SharePoint%20Framework%20package.html#create-app-catalog>`_ and go to **App Requests**.
Click **Plumsail HelpDesk Widget** on the requests list.

|Widget_AppCatalog|

Check the permissions granting to the app and click **Approve**.

|Widget_Approval|

Then go back to the site where you want to install the widget add-in and click it again.
Confirm that you **Trust It**.

|Widget_Installation|

When the installation is finished, the widget's icon color will be changed from pale to bright one in **Site contents**.

|Widget_PaleIcon|

|Widget_BrightIcon|

.. |WidgetView| image:: ../_static/img/widgetview.png
   :alt: HelpDesk Widget
.. |EmailSettings| image:: ../_static/img/settingsicon.png
   :alt: E-mail settings
.. |WidgetTab| image:: ../_static/img/tab.png
   :alt: Widget Tab
.. |NewWidget| image:: ../_static/img/newitem.png
   :alt: Create a new item
.. |WidgetMenu| image:: ../_static/img/newwidget.png
   :alt: Widget settings
.. |GenSPConfigID| image:: ../_static/img/widget-get-sp-config-id.png
   :alt: Generated HTML code
.. |EditPage| image:: ../_static/img/editpage.png
   :alt: Adding a widget to your site
.. |Finish| image:: ../_static/img/finish.png
   :alt: Inserting a widget
.. |Office365AdminCenter| image:: ../_static/img/widget-open-admin-center.png
.. |SharePointAdminCenter| image:: ../_static/img/widget-navigate-to-sharepoint-admin-center.png
.. |OpenAppCatalog| image:: ../_static/img/widget-open-app-catalog.png
.. |CreateAppCatalog| image:: ../_static/img/widget-create-app-catalog.png
.. |NewAppCatalog| image:: ../_static/img/widget-new-app-catalog.png
.. |UploadSPPKG| image:: ../_static/img/widget-upload-sppkg.png
.. |TenantScopedWP| image:: ../_static/img/widget-tenant-scoped-webpart.png
.. |PickWPOnModernPage| image:: ../_static/img/widget-pick-wp-on-modern-page.png
.. |ConfigureModernWP| image:: ../_static/img/widget-configure-modern-wp.png
.. |WidgetOnModernPage| image:: ../_static/img/widget-on-modern-page.png
.. |PickWPOnClassicPage| image:: ../_static/img/widget-pick-wp-on-classic-page.png
.. |WidgetOnClassicPage| image:: ../_static/img/widget-on-classic-page.png
.. |GenGeneratedHTML| image:: ../_static/img/widget-get-html.png
.. |Widget_Issue| image:: ../_static/img/ConfigurationGuide_Widget_Issue.png
   :alt: Widget Issue
.. |Widget_ApprovalRequest| image:: ../_static/img/ConfigurationGuide_Widget_RequestApproval.png
   :alt: Request Approval
.. |Widget_SendRequest| image:: ../_static/img/ConfigurationGuide_Widget_Request.png
   :alt: Send Request
.. |Widget_AppCatalog| image:: ../_static/img/ConfigurationGuide_Widget_AppCatalog.png
   :alt: App Catalog
   :width: 634px
.. |Widget_Approval| image:: ../_static/img/ConfigurationGuide_Widget_Approval.png
   :alt: Approval
   :width: 634px
.. |Widget_Installation| image:: ../_static/img/ConfigurationGuide_Widget_Installation.png
   :alt: Widget Installation
   :width: 634px
.. |Widget_PaleIcon| image:: ../_static/img/ConfigurationGuide_Widget_PaleIcon.png
   :alt: Widget's Pale Icon
.. |Widget_BrightIcon| image:: ../_static/img/ConfigurationGuide_Widget_BrightIcon.png
   :alt: Widget's Bright Icon

.. _this link: /Configuration%20Guide/deprecated/Widget.html
.. _internal names: ../How%20To/Find%20the%20internal%20name%20of%20SharePoint%20column.html