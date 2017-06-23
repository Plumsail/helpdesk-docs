Create a new chart
##################

.. raw:: html

		 <iframe width="560" height="315" src="https://www.youtube.com/embed/6nMujkdaN6s" frameborder="0" allowfullscreen></iframe>


In HelpDesk you have some built-in charts in `Repots`_ but you can create your own chart with the help of `Dashboard Designer`_. Here is step-by-step instruction how to do that.

First of all, download Dashboard Designer from `here`_. It will be automatically embedded into HelpDesk and you will find it in site contents.

|SiteCont|

For example, you want to figure out which department in your company has the largest amount of tickets. Note that Department is a custom field with a choice type of information.

To build a new chart head to  Reports and choose ‘Edit page’ in the ribbon menu. 

|Reports|

Choose page area there you’d like to put a chart and click on ‘Insert’ in the ribbon menu. Select ‘Plumsail chart’ and don’t forget to save a page.

|RibbonChart|

Some chart was inserted to the page and you can configure it now. Click on ‘Configure’ to run Dashboard Designer.

|configureChart|

Next, you need to input data, as you use SharePoint data as a data source, so define a list and its view. In this example, Tickets list is selected.

Then pick required fields and start a process.

|ListPick|

Finally, you are ready to create a chart. In Dashboard Designer you have plenty of choices for charts and graphs to select. According to this case the best way to visualize data is to choose column type graph.

|ChooseChart|

Click ‘Preview’ and enjoy a new chart which shows that administration department has more tickets than others.

|NewChart|

Save your chart and that's it.

.. |SiteCont| image:: /_static/img/DD-in-site-contents.jpg
   :alt: DD in site-contents
.. |Reports| image:: /_static/img/reports-icon.png
   :alt: Reports
.. |RibbonChart| image:: /_static/img/chart.jpg
   :alt: Inser a chart
.. |configureChart| image:: /_static/img/configure-chart.jpg
   :alt: Configure a chart
.. |ListPick| image:: /_static/img/lists-pick.jpg
   :alt: Pick a list
.. |ChooseChart| image:: /_static/img/choose-chart.jpg
   :alt: Choosу a chart type
.. |NewChart| image:: /_static/img/new-chart-1.jpg
   :alt: New chart



.. _Dashboard Designer: https://plumsail.com/sharepoint-dashboard-designer/
.. _here: https://plumsail.com/sharepoint-dashboard-designer/download/
.. _Repots: https://plumsail.com/docs/help-desk-o365/v1.x/User%20Guide/Reports.html