Appearance settings
###################

You can hide or display the SharePoint out of the box quick launch bar
as well as customize HelpDesk navigation.

.. note:: If you are using Plumsail HelpDesk with version older than 2.1.1, please follow  `this link <deprecated/Appearance%20(before%202.1.1).html>`_ to learn about forms customization for your version of HelpDesk.


Navigate to **Settings** tab using the left navbar:

Then click on the **Appearance** button. Now you can see the quick launch
display setting and a list of HelpDesk navigation elements.

|navigationsets|

Top menu customization 
~~~~~~~~~~~~~~~~~~~~~~

HelpDesk top menu is a set of links  with different ticket views. You can customize them by adding a new button with a view or URL to external site. You can drag the existing links to chnage their order as well.

To add a new item to top navigation, click “New top menu item”.

|NewTopMenu|

You will see a dialog window where you need provide a title for a new item and select ticket view. If you choose a link instead of view, please provide an URL.

|NewItem|

Don’t forget to save a new item. After adding this new element you can drga it to change the links' order 

|NewItemOrder|

If you have troubles with deleting the item, open your browser's console and type localStorage.clear() there. Then renew the page.


.. |SettingsIcon| image:: ../_static/img/settingsicon.png
   :alt: Settings Navigation Icon
.. |navigationsets| image:: ../_static/img/appearance.png
   :alt: Navigation Sets
.. |leftsidebar| image:: ../_static/img/navigation-1.png
   :alt: Left Side Bar
.. |navigationEdit| image:: ../_static/img/navigation_edit.png
   :alt: Navigation Edit
.. |NewTopMenu| image:: ../_static/img/new-top-menu.jpg
   :alt: New top menu item
.. |NewItem| image:: ../_static/img/new-top-menu-item-1.png
   :alt: Creation of the new item
.. |NewItemOrder| image:: ../_static/img/new-top-menu-item-order.gif
   :alt: Change the items order
