How to use HelpDesk REST API
====
| You can review API reference on this `page <https://helpdesk-services.plumsail.com/_api/swagger>`_.

| HelpDesk REST API relies on SharePoint's REST API, so you can use OData queries with such parameters: $select, $expand, $filter, $top and $skiptoken.

| First of all you must create an API key, this can be done on Settings -> API page.

| To make an API query you must include an API key in the "X-HD-ApiKey" HTTP header.

| All queries support SharePoint OData syntax, `this page explains how to use OData syntax with SharePoint <https://docs.microsoft.com/en-us/sharepoint/dev/sp-add-ins/use-odata-query-operations-in-sharepoint-rest-requests>`_

| By default all entities will contain only builtin fields, but you can query additional fields which will be placed in the "CustomFields" property.

| By default all queries will return the first 50 items, but you can return to a maximum of 100 items with the $top query option. Also you can page through returned items with the $skiptoken query option. Example usage (note single quotes in $skiptoken): _api/v4/tickets?$top=100&$skiptoken='Paged=TRUE&p_ID=5'.

| All Tickets list queries will not contain any attachments. To load particular ticket's attachments you must query this ticket and include query parameter "includeAttachments=true". All attachments will be returned as base64 encoded string.