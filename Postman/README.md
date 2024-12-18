# Postman collection for OpenText Core Fax and XM Fax

OpenText™ Core Fax and XM Fax™ are enterprise-grade digital fax solution offering businesses of all sizes the features and functionality to keep communications flowing.

The SOAP Web Services provide access to several features of the fax server in order to integrate them to custom applications.
With the Web Services, it is possible, for example to:
- send a fax (with profile information and/or attached files)
- access a user's fax list
- make actions on faxes
- manage fax boxes delegations
- manage phone books

[Click here]() to access the Postman collection


## Configuration

Drop the *XM Fax - OpenText.postman_collection.json* file into Postman to import the requests collection.

### Core Fax

Drop the *Core Fax Env.postman_environment.json* file into Postman to import the environment, then edit the *Current value* column to set the following variables:

- **account\_name**: Your enterprise account name.
- **auth\_token**: An access token key generated from your enterprise account. Can be found in the cloud portal.
- **app\_user_id**: A user account to be used to make the requests.
- **api\_endpoint**: You need to run the request `Get Endpoint URL` located inside the *XM Fax - OpenText* collection and *Cloud* folder. This will ensure you are making your request on the right server endpoint corresponding to your enterprise region.
- **fax\_number**: A fax number to send a fax to when running the requests.


### XM Fax OnPrem

Drop the *XM Fax Env.postman_environment.json* file into Postman to import the environment, then edit the *Current value* column to set the following variables:

- **api\_host**: The XM Fax server host (including the port). Example: 127.0.0.1:8443
- **auth\_user**: The username to use for authentication. Can we internal user, site administrator or system administrator. See tutorial **API Authentication** for exact format.
- **auth\_pwd**: The password of the **auth\_user**.
- **app\_user_id**: A user to be used to make the requests.


## Running the samples

Before running the samples, make sure you have selected the OpenText environment from the drop-down menu on the upper right side of the Postman window.

The requests are regrouped by functionality.

- Fax
    - Send: requests to send a fax.
    - Find: requests to find faxes or get a specific fax image.
    - Actions: requests to manage a fax.
    - Delegation: requests to manage fax boxes delegation.
- Phone book: requests to access and manage users phone book.
- User: requests to get user profile, verify password and manage user data.
- System: requests to get system information.


Some tests depend on each other.
For example, requests in `Actions` folder often depend on the results of the requests from the `Find` folder.
You are in such a case whenever you see a variable inside the request's body (like `{{outbound_fax_id}}`)

Some requests contain values in ALL\_CAPS (like `DEMO_USER_2`).
In this case, you need to specify a valid value for your system because the samples cannot deternine a suitable value by themselves.
