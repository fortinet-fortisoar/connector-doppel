## About the connector
Doppel is a next-generation AI security company that specializes in protecting organizations from social engineering attacks, impersonation, malicious ads, fake domains, and phishing campaigns.
<p>This document provides information about the Doppel Connector, which facilitates automated interactions, with a Doppel server using FortiSOAR&trade; playbooks. Add the Doppel Connector as a step in FortiSOAR&trade; playbooks and perform automated operations with Doppel.</p>

### Version information

Connector Version: 1.0.0


Authored By: Fortinet

Certified: No

## Installing the connector
<p>From FortiSOAR&trade; 5.0.0 onwards, use the <strong>Connector Store</strong> to install the connector. For the detailed procedure to install a connector, click <a href="https://docs.fortinet.com/document/fortisoar/0.0.0/installing-a-connector/1/installing-a-connector" target="_top">here</a>.<br>You can also use the following <code>yum</code> command as a root user to install connectors from an SSH session:</p>
`yum install cyops-connector-doppel`

## Prerequisites to configuring the connector
- You must have the URL of Doppel server to which you will connect and perform automated operations and credentials to access that server.
- The FortiSOAR&trade; server should have outbound connectivity to port 443 on the Doppel server.

## Minimum Permissions Required
- N/A

## Configuring the connector
For the procedure to configure a connector, click [here](https://docs.fortinet.com/document/fortisoar/0.0.0/configuring-a-connector/1/configuring-a-connector)
### Configuration parameters
<p>In FortiSOAR&trade;, on the Connectors page, click the <strong>Doppel</strong> connector row (if you are in the <strong>Grid</strong> view on the Connectors page) and in the <strong>Configurations&nbsp;</strong> tab enter the required configuration details:&nbsp;</p>
<table border=1><thead><tr><th>Parameter<br></th><th>Description<br></th></tr></thead><tbody><tr><td>Server URL<br></td><td>Specify the server URL of the Doppel server to connect and perform automated operations.<br>
<tr><td>API Key<br></td><td>Specify the API Key to connect to the endpoint and perform automated operations.<br>
<tr><td>Verify SSL<br></td><td>Specifies whether the SSL certificate for the server is to be verified or not. <br/>By default, this option is set as True.<br></td></tr>
</tbody></table>

## Actions supported by the connector
The following automated operations can be included in playbooks and you can also use the annotations to access operations from FortiSOAR&trade; release 4.10.0 and onwards:
<table border=1><thead><tr><th>Function<br></th><th>Description<br></th><th>Annotation and Category<br></th></tr></thead><tbody><tr><td>Get All Alerts<br></td><td>Retrieve a list of alerts from the Doppel server using the specified filter parameters.<br></td><td>get_all_alerts <br/>Investigation<br></td></tr>
<tr><td>Get Alert Details<br></td><td>Retrieve specific alert details from the Doppel server using the provided alert ID or entity.<br></td><td>get_alert_details <br/>Investigation<br></td></tr>
<tr><td>Update Alert<br></td><td>Update a specific alert on the Doppel server using the provided Alert ID or Entity, along with the input parameters you've specified.<br></td><td>update_alert <br/>Investigation<br></td></tr>
<tr><td>Execute an API Request<br></td><td>Sends an API request to an API endpoint based on specified HTTP method, endpoint, and other input parameters that you have specified, enabling flexible API interactions tailored to user needs.<br></td><td>execute_an_api_call <br/>Investigation<br></td></tr>
</tbody></table>

### operation: Get All Alerts

#### Input parameters
<table border=1><thead><tr><th>Parameter<br></th><th>Description<br></th></tr></thead><tbody><tr><td>Search Key<br></td><td>Specify a search key to filter alerts. Note: Currently, only URL-based searches are supported.<br>
</td></tr><tr><td>Queue State<br></td><td>Select a queue state to filter alerts. You can choose from the following options: Doppel Review, Needs Confirmation, Actioned, Taken Down, Monitoring, or Archived.<br>
</td></tr><tr><td>Product<br></td><td>Select the product category associated with the alerts. You can choose from the following options: Domains, Social Media, Mobile Apps, Ecommerce, Crypto, Email, Paid Ads, or Telco.<br>
</td></tr><tr><td>Created After<br></td><td>Select a date and time to retrieve alerts that include only those items that were created after the specified timestamp.<br>
</td></tr><tr><td>Created Before<br></td><td>Select a date and time to retrieve alerts that include only those items that were created before the specified timestamp.<br>
</td></tr><tr><td>Last Activity Timestamp<br></td><td>Select a date and time to retrieve results that include only those items that were last seen after the specified timestamp.<br>
</td></tr><tr><td>Sort Type<br></td><td>Select the sorting criteria for the retrieved alerts. You can choose from the following options: Date Sourced or Date Last Actioned.<br>
</td></tr><tr><td>Order By<br></td><td>Select the sort order for the retrieved alerts. You can choose from the following options: Ascending or Descending. By default, this option is set to "Descending".<br>
</td></tr><tr><td>Page Number<br></td><td>Specify the page number from which to retrieve alerts when pagination is applied. This parameter is used to fetch a specific subset of results based on the page number, helping to break large datasets into manageable chunks. By default, this value is set to 0.<br>
</td></tr><tr><td>Tags<br></td><td>Specify a comma-separated list of tags to filter the alerts.<br>
</td></tr></tbody></table>

#### Output
The output contains the following populated JSON schema:
<code><br>{
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "alerts": [
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        {
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "id": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "entity": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "brand": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "queue_state": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "entity_state": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "severity": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "product": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "platform": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "source": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "notes": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "created_at": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "screenshot_url": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "last_activity_timestamp": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "score": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "message": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "doppel_link": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "entity_content": {
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                "root_domain": {
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "domain": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "registrar": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "ip_address": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "country_code": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "hosting_provider": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "contact_email": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "mx_records": [],
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "nameservers": []
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                }
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            },
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "audit_logs": [
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                {
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "timestamp": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "type": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "value": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "changed_by": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    "metadata": {}
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                }
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            ],
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "tags": [],
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "uploaded_by": ""
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        }
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    ],
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "metadata": {
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        "count": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        "page": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        "total_pages": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        "page_size": ""
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    }
</code><code><br>}</code>
### operation: Get Alert Details
#### Input parameters
<table border=1><thead><tr><th>Parameter<br></th><th>Description<br></th></tr></thead><tbody><tr><td>Alert ID<br></td><td>Specify the alert ID to retrieve its details from the Doppel server. Note: You can provide either an Alert ID or an Entity. You can obtain the Alert ID from the response of the "Get All Alerts" action.<br>
</td></tr><tr><td>Entity<br></td><td>Specify the alert entity to retrieve its details from the Doppel server. Note: You may provide either an Alert ID or an Entity. You can obtain the Entity from the response of the "Get All Alerts" action.<br>
</td></tr></tbody></table>

#### Output
The output contains the following populated JSON schema:
<code><br>{
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "id": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "entity": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "brand": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "queue_state": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "entity_state": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "severity": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "product": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "platform": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "source": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "notes": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "created_at": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "screenshot_url": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "last_activity": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "score": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "message": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "doppel_link": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "entity_content": {
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        "root_domain": {
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "domain": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "registrar": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "ip_address": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "country_code": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "hosting_provider": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "contact_email": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "mx_records": [],
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "nameservers": []
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        }
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    },
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "audit_logs": [
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        {
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "timestamp": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "type": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "value": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "changed_by": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "metadata": {}
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        }
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    ],
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "tags": [],
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "uploaded_by": ""
</code><code><br>}</code>
### operation: Update Alert
#### Input parameters
<table border=1><thead><tr><th>Parameter<br></th><th>Description<br></th></tr></thead><tbody><tr><td>Alert ID<br></td><td>Specify the alert ID to update its details on the Doppel server. Note: You can provide either an Alert ID or an Entity. You can obtain the Alert ID from the response of the "Get All Alerts" action.<br>
</td></tr><tr><td>Entity<br></td><td>Specify the alert entity to update its details on the Doppel server. Note: You may provide either an Alert ID or an Entity. You can obtain the Entity from the response of the "Get All Alerts" action.<br>
</td></tr><tr><td>Queue State<br></td><td>Select the queue state to update the alert. You can choose from the following options: Doppel Review, Needs Confirmation, Actioned, Taken Down, Monitoring, or Archived.<br>
</td></tr><tr><td>Entity State<br></td><td>Select the entity state to update the alert. You can choose from the following options: Active, Down, or Parked.<br>
</td></tr><tr><td>Comment<br></td><td>Specify a comment to add to the alert.<br>
</td></tr><tr><td>Action on Tag<br></td><td>Select the type of action to perform on the tag. You can choose from the following options: Add or Remove.<br>
</td></tr><tr><td>Tag Name<br></td><td>Specify the tag name to be added or removed.<br>
</td></tr></tbody></table>

#### Output
The output contains the following populated JSON schema:
<code><br>{
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "id": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "entity": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "brand": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "queue_state": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "entity_state": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "severity": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "product": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "platform": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "source": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "notes": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "created_at": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "screenshot_url": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "last_activity": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "score": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "message": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "doppel_link": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "entity_content": {
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        "root_domain": {
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "domain": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "registrar": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "ip_address": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "country_code": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "hosting_provider": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "contact_email": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "mx_records": [],
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "nameservers": []
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        }
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    },
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "audit_logs": [
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        {
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "timestamp": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "type": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "value": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "changed_by": "",
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;            "metadata": {}
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        }
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    ],
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "tags": [],
</code><code><br>&nbsp;&nbsp;&nbsp;&nbsp;    "uploaded_by": ""
</code><code><br>}</code>
### operation: Execute an API Request
#### Input parameters
<table border=1><thead><tr><th>Parameter<br></th><th>Description<br></th></tr></thead><tbody><tr><td>HTTP Method<br></td><td>Select an HTTP action for the request. You can select from the following options:  

DELETE 

GET 

PATCH 

POST 

PUT <br>
</td></tr><tr><td>Endpoint<br></td><td>Specify the target API URL path for the request. For example, if the website is https://example.com and URL path is https://example.com/images/pic.jpg, the endpoint would be images/pic.jpg.<br>
</td></tr><tr><td>Query Parameters<br></td><td>(Optional) Specify any optional parameters to add to the URL and refine the request.<br>
</td></tr><tr><td>Request Payload<br></td><td>(Optional) Specify data, as JSON, to be sent as the request payload (typically for POST or PUT requests).<br>
</td></tr></tbody></table>

#### Output

 The output contains a non-dictionary value.
## Included playbooks
The `Sample - Doppel - 1.0.0` playbook collection comes bundled with the Doppel connector. These playbooks contain steps using which you can perform all supported actions. You can see bundled playbooks in the **Automation** > **Playbooks** section in FortiSOAR<sup>TM</sup> after importing the Doppel connector.

- Get All Alerts
- Get Alert Details
- Update Alert
- Execute an API Request

**Note**: If you are planning to use any of the sample playbooks in your environment, ensure that you clone those playbooks and move them to a different collection, since the sample playbook collection gets deleted during connector upgrade and delete.
