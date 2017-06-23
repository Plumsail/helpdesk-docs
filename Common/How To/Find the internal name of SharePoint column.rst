Find the internal name of SharePoint column
###########################################

Internal names are used to get field value and can be used in `trigger conditions`_, message templates or `workflows`_.

**The display name** is a name that was given to a column when it was created, and it is the name that is shown to end user. **The internal name** is obtained from display name but all special characters and spaces are replaced with Unicode. 

There are not so many options how to get the internal name and the easiest way is to copy it from query string.

For that, navigate to list settings.

|ListSettings|

Choose column which internal name you’d like to get.

|Columns|

And then take a look at URL.

|URL|

Underscores are converted to %5F, you can use `any online decoder`_ to make it look more pleasant or just replace %5F with ‘_’. So, internal field name — Order_x0020_Number. Note one more time – Order%5Fx0020%5FNumber means the same as Order_x0020_Number. 

Important to notice that the internal name is set only once and it stays immutable even if you have changed the display name. 

Small trick on how to avoid this confusing experience with replacing Unicode — you can create a column which Display name has no spaces and after Internal name has been generated, just add spaces to Display name wherever necessary. This way, Internal name will be preserved in its original form with no underscores.


.. |ListSettings| image:: /_static/img/list-settings-1.jpg
   :alt: List settings
.. |Columns| image:: /_static/img/columns.jpg
   :alt: Columns
.. |URL| image:: /_static/img/internal-name-in-url.jpg
   :alt: Internal name in URL

.. _trigger conditions: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Triggers.html
.. _workflows: https://plumsail.com/docs/help-desk-o365/v1.x/Configuration%20Guide/Triggers.html#start-workflow
.. _any online decoder: http://meyerweb.com/eric/tools/dencoder/