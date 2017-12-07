Data protection policy
###################

Application security
--------------------

Plumsail HelpDesk is hosted in Microsoft Azure. The infrastructure for databases and application servers is managed and maintained by `Azure`_.

We are seriously concerned about your security, so, everything from engineering to deployment performed with our highest standards of security. Our source code repositories are regularly scanned for security issues and our network is protected by a firewall.

We have a QA department which reviews and test our code for any security vulnerabilities. Testing is occurred in a separate environment from production. We don't use any customer's data during testing.

Also, we are using IDS technologies to monitor our network for malicious activity or policy violations.

Data security
-------------

Plumsail HelpDesk collects very few information about customers - only SharePoint Online domain name and URLs of HelpDesk installations are required for license validation. After installing Plumsail HelpDesk, the only data that we are gathering from you is application logs from the system.

Whenever your data is in transit between you and us, everything is encrypted and sent using HTTPS. Data at rest is encrypted using `AES 256`_ bit standards (one of the strongest block ciphers available) with keys managed by Azure Storage Service Encryption. Data in transit is encrypted with SSL/TLS protocols.

In HelpDesk we use a multi-tenant data model, so each user has a unique tenant ID and only logged-in and verified users can have an access to the application.

Access to data of your help desk governed by access rights and can be configured to different permission levels.

All that data is stored in Microsoft Azure. Backups are taken every day. Application logs are stored for a week.


Business transactions
---------------------

We protect your billing information. All transactions are processed through secure encryption and sensitive data are transmitted, stored and processed on PCI DSS network.

Physical security
-----------------

Plumsail HelpDesk hosts all data in Microsoft Azure which data centers have been tested for security, availability and business continuity. For more information, take a look at `this link`_.
`Disaster recovery program`_ ensures that our services will be available or are easily recoverable in the case of any catastrophe.

GDPR
----

Plumsail prioritizes customer trust. We know that customer data is important to our customers’ values and operations. That is why we keep it private and safe. This section describes compliance with General Data Protection Regulation (“GDPR”), which becomes enforceable on May 25, 2018.

Informaiton that we collect about you as a customer is describe in our general `privacy policy </privacy-policy/>`_. You, as a customer, have rights and ability to:
 - Access your personal data
 - Correct errors in their personal data
 - Erase your personal data
 - Object to processing of your personal data
 - Export personal data

Plumsail HelpDesk is installed directly into SharePoint tenant of a client. All personal data of HelpDesk requesters and agents is stored inside tenant of a client. Thus, Microsoft GDPR policies are applied here.

However, Plumsail provides services for conversion of email messages into tickets. Physical location of those services is inside Europian Union. All date is properly protected and encrypted while processing as described in our `data protection <Security>`_ and in `privacy </privacy-policy/helpdesk/>`_ policies. 

Plumsail is implementing necessary data breaches notifications for relevant supervisory authorities and data subjects in accordance with GDPR timeframes.

Compliance Certifications
--------------------

Azure data center is certified for ISO 27001, SOC I, II AND III, HIPPA and FedRAMP compliance. Visit `Azure trust center`_. 

Get in touch with us
---------------------
If you have any questions about our security policy, please, feel free to drop a line at support@plumsail.com.


.. _Azure: https://www.microsoft.com/en-us/trustcenter/Security/AzureSecurity
.. _AES 256: https://en.wikipedia.org/wiki/Advanced_Encryption_Standard
.. _this link: https://www.microsoft.com/en-us/trustcenter/Security/AzureSecurity
.. _Disaster recovery program: https://azure.microsoft.com/en-us/documentation/articles/resiliency-disaster-recovery-high-availability-azure-applications/
.. _Azure trust center: https://azure.microsoft.com/en-us/support/trust-center/
