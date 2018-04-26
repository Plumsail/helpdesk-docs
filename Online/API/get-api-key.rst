Get API key
=======================================

Generate API key
----------------

To generate new API key for Microsoft Flow connector or REST API you need to navigate to the Settings -> API page on your HelpDesk site and click "Create new" button. Then select type of API key according to your needs. Read-only keys can be used only to retrive information, Edit keys allow to update and create items.

.. image:: ../_static/img/create-api-key.png
   :alt: API keys

.. image:: ../_static/img/create-api-key-form.png
   :alt: API key type

Copy and use API key
--------------------

Once you created and API key, you can see your key right in the "API key" row on a key form:

.. image:: ../_static/img/copy-api-key.png
   :alt: API key

|

Now you can copy and use it in:

- `Microsoft Flow <use-from-flow.html>`_
- `REST API calls <use-as-rest-api.html>`_

.. note::
	Only users with Manage Web permissions and above can view and create API keys.

.. note::
	If you don't have Settings -> API page, please check your HelpDesk version, it should be 1.4.5 or above to use API.