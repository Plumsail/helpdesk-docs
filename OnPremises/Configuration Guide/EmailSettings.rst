Email settings
##############

You can configure HelpDesk to create new tickets or ticket comments with
email messages as well as specify some custom settings for the email
address used for notifications.

Navigate to settings using the icon on the navbar:

|SettingsIcon|

You will see “Email settings” section.

|HDEmailSettings|

Incoming email settings
~~~~~~~~~~~~~~~~~~~~~~~

If you want to receive new tickets from your support email address you need to configure incoming email settings:

|IncomingEmail|

Outgoing email settings
~~~~~~~~~~~~~~~~~~~~~~~

To send notifications HelpDesk needs SMTP server settings. Fill in SMTP server settings:

|OutgoingEmailSettings|

By default HelpDesk uses the same address and password as you specified in incoming settings. But you can uncheck this option and specify them manually:

|OutgoingEmailSettings1|

Email messages synchronization
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can notice small widget “Sync service status” at the first picture. It is responsible for conversion of incoming email messages into tickets. Click “Start” to enable synchronization:

|MessageSync|

You can choose “Sync from current date” or “Sync from specific date”. Second option is especially useful if you have a lot of messages in your inbox and want to start synchronization from current date without conversion of old messages to tickets.

Once you started sync service, it will run synchronization periodically (5 minutes interval). If you want to sync messages right now, click “Sync now”:

|MessageSync1|

You can interrupt synchronization any time by stopping the service. 


.. |SettingsIcon| image:: /_static/img/settingsicon.png
   :alt: Settings Navigation Icon
.. |HDEmailSettings| image:: /_static/img/email_settings5.png
   :alt: Email Settings
.. |IncomingEmail| image:: /_static/img/HD_ImapSettings_2013.png
   :alt: Incoming email settings
.. |OutgoingEmailSettings| image:: /_static/img/HD_SMTPSettings2013.png
   :alt: Outgoing email settings
.. |OutgoingEmailSettings1| image:: /_static/img/HD_EmailSettings2013_full.png
   :alt: Outgoing email settings
.. |MessageSync| image:: /_static/img/start_sync1.png
   :alt: Sync service status
.. |MessageSync1| image:: /_static/img/sync_now.png
   :alt: Sync now