Email settings
###########################

You can configure HelpDesk to create new tickets or ticket comments with
email messages as well as specify some custom settings for the email
address used for notifications.

Navigate to settings using the icon on the navbar:

|SettingsIcon|

You will see “Email settings” section.

|HDEmailSettings|

.. _forwarding:

Forwarding of e-mail messages from your support mailbox
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. toctree::
   :hidden:
   :name: emailforwardtoc
   
   How forwarding works

If you want to receive new tickets sent to your support email in
HelpDesk, you’ll need to configure e-mail forwarding. Take a look at the
email address in the Screenshot above. It was created automatically
during HelpDesk installation.

If you send a message to this address, it will appear in HelpDesk as a
new ticket. If you reply to this message directly or via HelpDesk, the
reply will appear as a comment in a ticket discussion. This mailbox is
used to create tickets and comments in real time and does not store your
messages. You can find more information in \ `this article`_.

You can use this address as the support email address of HelpDesk, but
most likely you already have your own support e-mail address. That is
why you may want to configure e-mail forwarding from your address to
HelpDesk.

Create a rule in your mailbox to forward incoming email messages to
HelpDesk address. Here is a list of instructions on how to set up e-mail
forwarding for some of the most popular platforms:

-  `Office 365 Outlook`_
-  `Outlook.com`_
-  `Gmail`_
-  `Yahoo`_

Change the reply address and email display name
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

By default, HelpDesk will use the auto generated email address for sending
notifications. You can specify your own “Reply to” address, so your
customers will reply to your own support mailbox.

You also can specify a friendly display name for your email address. By
default, it is “HelpDesk”.

|HDEmailSettingsReply|

Custom SMTP server settings
~~~~~~~~~~~~~~~~~~~~~~~~~~~

By default, HelpDesk will use the auto generated email address for
sending notifications. You can specify a custom “Reply to” address as
described above, but alternatively, you can specify SMTP server settings
for your support mailbox to make HelpDesk use your support mailbox for
sending messages. To do it click “Custom SMTP server settings”. You will
see a few parameters. Fill them in by following your SMTP server’s
instructions and click “Save”. Also, you can test the correctness of entered settings by clicking on "Test" button.

|HDSMTPServerSettings|

.. _this article: How%20forwarding%20works.html
.. _Office 365 Outlook: https://support.office.com/en-sg/article/Use-rules-in-Outlook-Web-App-to-automatically-forward-messages-to-another-account-1433e3a0-7fb0-4999-b536-50e05cb67fed#__toc377639463
.. _Outlook.com: http://windows.microsoft.com/en-us/outlook/multiple-email-accounts#msaForwardEmail
.. _Gmail: https://support.google.com/mail/answer/10957?hl=en
.. _Yahoo: https://help.yahoo.com/kb/SLN3525.html

.. |SettingsIcon| image:: /_static/img/settingsicon.png
   :alt: Settings Navigation Icon
.. |HDEmailSettings| image:: /_static/img/email-settings-0.png
   :alt: Email Settings
.. |HDEmailSettingsReply| image:: /_static/img/email-settings-1.png
   :alt: Email Reply Settings
.. |HDSMTPServerSettings| image:: /_static/img/email-settings-2.png
   :alt: SMTP Server Settings