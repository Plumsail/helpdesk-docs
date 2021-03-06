Ticket numbering customization
###############################

.. note:: This feature is available in version 1.5.5 and above.

Ticket number is used to identify a ticket:

* in e-mail notifications
* on the edit and view forms
* in ticket list views.

Sometimes it can be useful to make custom numbering. 
For example, to distinguish tickets from different HelpDesk, 
or to include additional information to the ticket number (date, time, department name).

You can configure tickets numbering. 

Navigate to the **Settings** page using the left navbar:

Then click on the **Ticket numbering** button. Now you can see the ticket numbering settings.

|PageExample|

Formula customization
~~~~~~~~~~~~~~~~~~~~~

By default, the formula is ``{{IDCounter}}``, so tickets are numbered as "1", "2" etc. 

A formula must contain ``{{IDCounter}}`` token and may contain optional ``{{CurrentDate}}`` token.

``{{IDCounter}}`` is an HelpDesk-wide ticket counter. 

``{{CurrentDate}}`` is current date/time.

You can use ``{{CurrentDate:format}}`` syntax to show only part of current date/time. 

+--------+---------------------------------------------+------------------------+
| Format | Example formula                             | Example Ticket number  |
+========+=============================================+========================+
| t      | ``IT {{IDCounter}} {{CurrentDate:t}}``      | IT 123 9:34 PM         |
+--------+---------------------------------------------+------------------------+
| d      | ``IT {{IDCounter}} {{CurrentDate:d}}``      | IT 123 2/15/2019       |
+--------+---------------------------------------------+------------------------+
| HH-mm  | ``IT {{IDCounter}} {{CurrentDate:HH-mm}}``  | IT 123 21-34           |
+--------+---------------------------------------------+------------------------+

Learn more about
`standard <https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings?view=netframework-4.7.2>`_
or `custom <https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.7.2>`_
format strings.

As you can see, ``{{CurrentDate:HH-mm}}`` will show only hours and minutes in 24h format. 
So, you can change formula to ``IT {{IDCounter}} {{CurrentDate:HH-mm}}``.

|CustomFormula|

In this case new tickets will be numbered as "IT 31 09-19", "IT 32 09-21", "IT 33 09-22" etc

|CustomNumbering|

Reset IDCounter
~~~~~~~~~~~~~~~~

You can reset IDCounter value using "Reset IDCounter" button. 
For example, It may be useful if you are moving from test to production use.

Click "Advanced settings" to see current IDCounter value.

|Advanced|

Click "Reset IDCounter" to reset IDCounter to zero.

.. warning::
    Use this option only if you are absolutely sure that there are no tickets with a new counter value in HelpDesk. 
    Otherwise, it will lead to the appearance of tickets with duplicate IDs.


.. |PageExample| image:: ../_static/img/ticket-numbering-page.png
   :alt: Ticket numbering settings page
.. |Advanced| image:: ../_static/img/ticket-numbering-advanced.png
   :alt: Ticket numbering settings page expanded
.. |CustomFormula| image:: ../_static/img/custom-formula.png
   :alt: Custom formula
.. |CustomNumbering| image:: ../_static/img/custom-ticket-numbering.png
   :alt: Custom ticket numbering demo
