# Go API client for linodegogen

# Introduction
The Linode API provides the ability to programmatically manage the full
range of Linode products and services.

This reference is designed to assist application developers and system
administrators.  Each endpoint includes descriptions, request syntax, and
examples using standard HTTP requests. Response data is returned in JSON
format.


This document was generated from our OpenAPI Specification.  See the
<a target=\"_top\" href=\"https://www.openapis.org\">OpenAPI website</a> for more information.

<a target=\"_top\" href=\"https://developers.linode.com/api/docs/v4/openapi.yaml\">Download the Linode OpenAPI Specification</a>.


# Changelog

<a target=\"_top\" href=\"https://developers.linode.com/changelog\">View our Changelog</a> to see release
notes on all changes made to our API.

# Access and Authentication

Some endpoints are publicly accessible without requiring authentication.
All endpoints affecting your Account, however, require either a Personal
Access Token or OAuth authentication (when using third-party
applications).

## Personal Access Token

The easiest way to access the API is with a Personal Access Token (PAT)
generated from the
<a target=\"_top\" href=\"https://cloud.linode.com/profile/tokens\">Linode Cloud Manager</a> or
the [Create Personal Access Token](/api/v4/profile-tokens#post) endpoint.

All scopes for the OAuth security model ([defined below](#o-auth)) apply to this
security model as well.

### Authentication

| Security Scheme Type: | HTTP |
|-----------------------|------|
| **HTTP Authorization Scheme** | bearer |

## OAuth
If you only need to access the Linode API for personal use,
we recommend that you create a [personal access token](#personal-access-token).
If you're designing an application that can authenticate with an arbitrary Linode user, then
you should use the OAuth 2.0 workflows presented in this section.

For a more detailed example of an OAuth 2.0 implementation, see our guide on [How to Create an OAuth App with the Linode Python API Library](https://www.linode.com/docs/platform/api/how-to-create-an-oauth-app-with-the-linode-python-api-library/#oauth-2-authentication-exchange).

Before you implement OAuth in your application, you first need to create an OAuth client. You can do this [with the Linode API](https://developers.linode.com/api/v4/account-oauth-clients/#post) or [via the Cloud Manager](https://cloud.linode.com/profile/clients):

  - When creating the client, you'll supply a `label` and a `redirect_uri` (referred to as the Callback URL in the Cloud Manager).
  - The response from this endpoint will give you a `client_id` and a `secret`.
  - Clients can be public or private, and are private by default. You can choose to make the client public when it is created.
    - A private client is used with applications which can securely store the client secret (that is, the secret returned to you when you first created the client). For example, an application running on a secured server that only the developer has access to would use a private OAuth client. This is also called a confidential client in some OAuth documentation.
    - A public client is used with applications where the client secret is not guaranteed to be secure. For example, a native app running on a user's computer may not be able to keep the client secret safe, as a user could potentially inspect the source of the application. So, native apps or apps that run in a user's browser should use a public client.
    - Public and private clients follow different workflows, as described below.

### OAuth Workflow

The OAuth workflow is a series of exchanges between your third-party app and Linode. The workflow is used
to authenticate a user before an application can start making API calls on the user's behalf.

Notes:

- With respect to the diagram in [section 1.2 of RFC 6749](https://tools.ietf.org/html/rfc6749#section-1.2), login.linode.com (referred to in this section as the *login server*)
is the Resource Owner and the Authorization Server; api.linode.com (referred to here as the *api server*) is the Resource Server.
- The OAuth spec refers to the private and public workflows listed below as the [authorization code flow](https://tools.ietf.org/html/rfc6749#section-1.3.1) and [implicit flow](https://tools.ietf.org/html/rfc6749#section-1.3.2).

| PRIVATE WORKFLOW | PUBLIC WORKFLOW |
|------------------|------------------|
| 1.  The user visits the application's website and is directed to login with Linode. | 1.  The user visits the application's website and is directed to login with Linode. |
| 2.  Your application then redirects the user to Linode's [login server](https://login.linode.com) with the client application's `client_id` and requested OAuth `scope`, which should appear in the URL of the login page. | 2.  Your application then redirects the user to Linode's [login server](https://login.linode.com) with the client application's `client_id` and requested OAuth `scope`, which should appear in the URL of the login page. |
| 3.  The user logs into the login server with their username and password. | 3.  The user logs into the login server with their username and password. |
| 4.  The login server redirects the user to the specificed redirect URL with a temporary authorization `code` (exchange code) in the URL. | 4.  The login server redirects the user back to your application with an OAuth `access_token` embedded in the redirect URL's hash. This is temporary and expires in two hours. No `refresh_token` is issued. Therefore, once the `access_token` expires, a new one will need to be issued by having the user log in again. |
| 5.  The application issues a POST request (*see below*) to the login server with the exchange code, `client_id`, and the client application's `client_secret`. | |
| 6.  The login server responds to the client application with a new OAuth `access_token` and `refresh_token`. The `access_token` is set to expire in two hours. | |
| 7.  The `refresh_token` can be used by contacting the login server with the `client_id`, `client_secret`, and `refresh_token` to get a new OAuth `access_token` and `refresh_token`. The new `access_token` is good for another two hours, and the new `refresh_token`, can be used to extend the session again by this same method. | |

### OAuth Private Workflow - Additional Details

The following information expands on steps 5 through 7 of the private workflow:

Once the user has logged into Linode and you have received an exchange code,
you will need to trade that exchange code for an `access_token` and `refresh_token`. You
do this by making an HTTP POST request to the following address:

```
https://login.linode.com/oauth/token
```

Make this request as `application/x-www-form-urlencoded` or as
`multipart/form-data` and include the following parameters in the POST body:

| PARAMETER | DESCRIPTION |
|-----------|-------------|
| client_id | Your app's client ID. |
| client_secret | Your app's client secret. |
| code | The code you just received from the redirect. |

You'll get a response like this:

```json
{
  \"scope\": \"linodes:read_write\",
  \"access_token\": \"03d084436a6c91fbafd5c4b20c82e5056a2e9ce1635920c30dc8d81dc7a6665c\"
  \"token_type\": \"bearer\",
  \"expires_in\": 7200,
}
```

Included in the reponse is an `access_token`. With this token, you can proceed to make
authenticated HTTP requests to the API by adding this header to each request:

```
Authorization: Bearer 03d084436a6c91fbafd5c4b20c82e5056a2e9ce1635920c30dc8d81dc7a6665c
```

### OAuth Reference

| Security Scheme Type | OAuth 2.0 |
|-----------------------|--------|
| **Authorization URL** | https://login.linode.com/oauth/authorize |
| **Token URL** | https://login.linode.com/oauth/token |
| **Scopes** | <ul><li>`account:read_only` - Allows access to GET information about your Account.</li><li>`account:read_write` - Allows access to all endpoints related to your Account.</li><li>`domains:read_only` - Allows access to GET Domains on your Account.</li><li>`domains:read_write` - Allows access to all Domain endpoints.</li><li>`events:read_only` - Allows access to GET your Events.</li><li>`events:read_write` - Allows access to all endpoints related to your Events.</li><li>`images:read_only` - Allows access to GET your Images.</li><li>`images:read_write` - Allows access to all endpoints related to your Images.</li><li>`ips:read_only` - Allows access to GET your ips.</li><li>`ips:read_write` - Allows access to all endpoints related to your ips.</li><li>`linodes:read_only` - Allows access to GET Linodes on your Account.</li><li>`linodes:read_write` - Allow access to all endpoints related to your Linodes.</li><li>`lke:read_only` - Allows access to GET LKE Clusters on your Account.</li><li>`lke:read_write` - Allows access to all endpoints related to LKE Clusters on your Account.</li><li>`longview:read_only` - Allows access to GET your Longview Clients.</li><li>`longview:read_write` - Allows access to all endpoints related to your Longview Clients.</li><li>`nodebalancers:read_only` - Allows access to GET NodeBalancers on your Account.</li><li>`nodebalancers:read_write` - Allows access to all NodeBalancer endpoints.</li><li>`stackscripts:read_only` - Allows access to GET your StackScripts.</li><li>`stackscripts:read_write` - Allows access to all endpoints related to your StackScripts.</li><li>`volumes:read_only` - Allows access to GET your Volumes.</li><li>`volumes:read_write` - Allows access to all endpoints related to your Volumes.</li></ul><br />|

# Requests

Requests must be made over HTTPS to ensure transactions are encrypted. The
following Request methods are supported:

| METHOD | USAGE |
|--------|-------|
| GET    | Retrieves data about collections and individual resources. |
| POST   | For collections, creates a new resource of that type. Also used to perform actions on action endpoints. |
| PUT    | Updates an existing resource. |
| DELETE | Deletes a resource. This is a destructive action. |


# Responses

Actions will return one following HTTP response status codes:

| STATUS  | DESCRIPTION |
|---------|-------------|
| 200 OK  | The request was successful. |
| 204 No Content | The server successfully fulfilled the request and there is no additional content to send. |
| 400 Bad Request | You submitted an invalid request (missing parameters, etc.). |
| 401 Unauthorized | You failed to authenticate for this resource. |
| 403 Forbidden | You are authenticated, but don't have permission to do this. |
| 404 Not Found | The resource you're requesting does not exist. |
| 429 Too Many Requests | You've hit a rate limit. |
| 500 Internal Server Error | Please [open a Support Ticket](/api/v4/support-tickets/#post). |

# Errors

Success is indicated via <a href=\"https://en.wikipedia.org/wiki/List_of_HTTP_status_codes\" target=\"_top\">Standard HTTP status codes</a>.
`2xx` codes indicate success, `4xx` codes indicate a request error, and
`5xx` errors indicate a server error. A
request error might be an invalid input, a required parameter being omitted,
or a malformed request. A server error means something went wrong processing
your request. If this occurs, please
[open a Support Ticket](/api/v4/support-tickets/#post)
and let us know. Though errors are logged and we work quickly to resolve issues,
opening a ticket and providing us with reproducable steps and data is always helpful.

The `errors` field is an array of the things that went wrong with your request.
We will try to include as many of the problems in the response as possible,
but it's conceivable that fixing these errors and resubmitting may result in
new errors coming back once we are able to get further along in the process
of handling your request.


Within each error object, the `field` parameter will be included if the error
pertains to a specific field in the JSON you've submitted. This will be
omitted if there is no relevant field. The `reason` is a human-readable
explanation of the error, and will always be included.

# Pagination

Resource lists are always paginated. The response will look similar to this:

```json
{
    \"data\": [ ... ],
    \"page\": 1,
    \"pages\": 3,
    \"results\": 300
}
```

* Pages start at 1. You may retrieve a specific page of results by adding
`?page=x` to your URL (for example, `?page=4`). If the value of `page`
exceeds `2^64/page_size`, the last possible page will be returned.


* Page sizes default to 100,
and can be set to return between 25 and 100. Page size can be set using
`?page_size=x`.

# Filtering and Sorting

Collections are searchable by fields they include, marked in the spec as
`x-linode-filterable: true`. Filters are passed
in the `X-Filter` header and are formatted as JSON objects. Here is a request
call for Linode Types in our \"standard\" class:

```Shell
curl \"https://api.linode.com/v4/linode/types\" \\
  -H '
    X-Filter: {
      \"class\": \"standard\"
    }'
```

The filter object's keys are the keys of the object you're filtering,
and the values are accepted values. You can add multiple filters by
including more than one key. For example, filtering for \"standard\" Linode
Types that offer one vcpu:

```Shell
 curl \"https://api.linode.com/v4/linode/types\" \\
  -H '
    X-Filter: {
      \"class\": \"standard\",
      \"vcpus\": 1
    }'
```

In the above example, both filters are combined with an \"and\" operation.
However, if you wanted either Types with one vcpu or Types in our \"standard\"
class, you can add an operator:

 ```Shell
curl \"https://api.linode.com/v4/linode/types\" \\
  -H '
    X-Filter: {
      \"+or\": [
        { \"vcpus\": 1 },
        { \"class\": \"standard\" }
      ]
    }'
```

Each filter in the `+or` array is its own filter object, and all conditions
in it are combined with an \"and\" operation as they were in the previous example.

Other operators are also available. Operators are keys of a Filter JSON
object. Their value must be of the appropriate type, and they are evaluated
as described below:

| OPERATOR | TYPE   | DESCRIPTION                       |
|----------|--------|-----------------------------------|
| +and     | array  | All conditions must be true.       |
| +or      | array  | One condition must be true.        |
| +gt      | number | Value must be greater than number. |
| +gte     | number | Value must be greater than or equal to number. |
| +lt      | number | Value must be less than number. |
| +lte     | number | Value must be less than or equal to number. |
| +contains | string | Given string must be in the value. |
| +neq      | string | Does not equal the value.          |
| +order_by | string | Attribute to order the results by - must be filterable. |
| +order    | string | Either \"asc\" or \"desc\". Defaults to \"asc\". Requires `+order_by`. |

For example, filtering for [Linode Types](/api/v4/linode-types)
that offer memory equal to or higher than 61440:

```Shell
curl \"https://api.linode.com/v4/linode/types\" \\
  -H '
    X-Filter: {
      \"memory\": {
        \"+gte\": 61440
      }
    }'
```

You can combine and nest operators to construct arbitrarily-complex queries.
For example, give me all [Linode Types](/api/v4/linode-types)
which are either `standard` or `highmem` class, or
have between 12 and 20 vcpus:

```Shell
curl \"https://api.linode.com/v4/linode/types\" \\
  -H '
    X-Filter: {
      \"+or\": [
        {
          \"+or\": [
            {
              \"class\": \"standard\"
            },
            {
              \"class\": \"highmem\"
            }
          ]
        },
        {
          \"+and\": [
            {
              \"vcpus\": {
                \"+gte\": 12
              }
            },
            {
              \"vcpus\": {
                \"+lte\": 20
              }
            }
          ]
        }
      ]
    }'
```

# CLI (Command Line Interface)

The <a href=\"https://github.com/linode/linode-cli\" target=\"_top\">Linode CLI</a> allows you to easily
work with the API using intuitive and simple syntax. It requires a
[Personal Access Token](#section/Personal-Access-Token)
for authentication, and gives you access to all of the features and functionality
of the Linode API that are documented here with CLI examples.

Endpoints that do not have CLI examples are currently unavailable through the CLI, but
can be accessed via other methods such as Shell commands and other third-party applications.


## Overview
This API client was generated by the [OpenAPI Generator](https://openapi-generator.tech) project.  By using the [OpenAPI-spec](https://www.openapis.org/) from a remote server, you can easily generate an API client.

- API version: 4.60.0
- Package version: 1.0.0
- Build package: org.openapitools.codegen.languages.GoClientCodegen

## Installation

Install the following dependencies:

```shell
go get github.com/stretchr/testify/assert
go get golang.org/x/oauth2
go get golang.org/x/net/context
go get github.com/antihax/optional
```

Put the package under your project folder and add the following in import:

```golang
import "./linodegogen"
```

## Documentation for API Endpoints

All URIs are relative to *https://api.linode.com/v4*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountApi* | [**CancelAccount**](docs/AccountApi.md#cancelaccount) | **Post** /account/cancel | Cancel Account
*AccountApi* | [**CreateClient**](docs/AccountApi.md#createclient) | **Post** /account/oauth-clients | Create OAuth Client
*AccountApi* | [**CreateCreditCard**](docs/AccountApi.md#createcreditcard) | **Post** /account/credit-card | Add/Edit Credit Card
*AccountApi* | [**CreatePayPalPayment**](docs/AccountApi.md#createpaypalpayment) | **Post** /account/payments/paypal | Stage PayPal Payment
*AccountApi* | [**CreatePayment**](docs/AccountApi.md#createpayment) | **Post** /account/payments | Make Payment
*AccountApi* | [**CreateUser**](docs/AccountApi.md#createuser) | **Post** /account/users | Create User
*AccountApi* | [**DeleteClient**](docs/AccountApi.md#deleteclient) | **Delete** /account/oauth-clients/{clientId} | Delete OAuth Client
*AccountApi* | [**DeleteUser**](docs/AccountApi.md#deleteuser) | **Delete** /account/users/{username} | Delete User
*AccountApi* | [**EnableAccountManged**](docs/AccountApi.md#enableaccountmanged) | **Post** /account/settings/managed-enable | Enable Linode Managed
*AccountApi* | [**EventRead**](docs/AccountApi.md#eventread) | **Post** /account/events/{eventId}/read | Mark Event as Read
*AccountApi* | [**EventSeen**](docs/AccountApi.md#eventseen) | **Post** /account/events/{eventId}/seen | Mark Event as Seen
*AccountApi* | [**ExecutePayPalPayment**](docs/AccountApi.md#executepaypalpayment) | **Post** /account/payments/paypal/execute | Execute Staged/Approved PayPal Payment
*AccountApi* | [**GetAccount**](docs/AccountApi.md#getaccount) | **Get** /account | View Account
*AccountApi* | [**GetAccountSettings**](docs/AccountApi.md#getaccountsettings) | **Get** /account/settings | View Account Settings
*AccountApi* | [**GetClient**](docs/AccountApi.md#getclient) | **Get** /account/oauth-clients/{clientId} | View OAuth Client
*AccountApi* | [**GetClientThumbnail**](docs/AccountApi.md#getclientthumbnail) | **Get** /account/oauth-clients/{clientId}/thumbnail | View OAuth Client Thumbnail
*AccountApi* | [**GetClients**](docs/AccountApi.md#getclients) | **Get** /account/oauth-clients | List OAuth Clients
*AccountApi* | [**GetEvent**](docs/AccountApi.md#getevent) | **Get** /account/events/{eventId} | View Event
*AccountApi* | [**GetEvents**](docs/AccountApi.md#getevents) | **Get** /account/events | List Events
*AccountApi* | [**GetInvoice**](docs/AccountApi.md#getinvoice) | **Get** /account/invoices/{invoiceId} | View Invoice
*AccountApi* | [**GetInvoiceItems**](docs/AccountApi.md#getinvoiceitems) | **Get** /account/invoices/{invoiceId}/items | List Invoice Items
*AccountApi* | [**GetInvoices**](docs/AccountApi.md#getinvoices) | **Get** /account/invoices | List Invoices
*AccountApi* | [**GetNotifications**](docs/AccountApi.md#getnotifications) | **Get** /account/notifications | List Notifications
*AccountApi* | [**GetPayment**](docs/AccountApi.md#getpayment) | **Get** /account/payments/{paymentId} | View Payment
*AccountApi* | [**GetPayments**](docs/AccountApi.md#getpayments) | **Get** /account/payments | List Payments
*AccountApi* | [**GetTransfer**](docs/AccountApi.md#gettransfer) | **Get** /account/transfer | View Network Utilization
*AccountApi* | [**GetUser**](docs/AccountApi.md#getuser) | **Get** /account/users/{username} | View User
*AccountApi* | [**GetUserGrants**](docs/AccountApi.md#getusergrants) | **Get** /account/users/{username}/grants | View User&#39;s grants
*AccountApi* | [**GetUsers**](docs/AccountApi.md#getusers) | **Get** /account/users | List Users
*AccountApi* | [**ResetClientSecret**](docs/AccountApi.md#resetclientsecret) | **Post** /account/oauth-clients/{clientId}/reset-secret | Reset OAuth Client Secret
*AccountApi* | [**SetClientThumbnail**](docs/AccountApi.md#setclientthumbnail) | **Put** /account/oauth-clients/{clientId}/thumbnail | Update OAuth Client Thumbnail
*AccountApi* | [**UpdateAccount**](docs/AccountApi.md#updateaccount) | **Put** /account | Update Account
*AccountApi* | [**UpdateAccountSettings**](docs/AccountApi.md#updateaccountsettings) | **Put** /account/settings | Update Account Settings
*AccountApi* | [**UpdateClient**](docs/AccountApi.md#updateclient) | **Put** /account/oauth-clients/{clientId} | Update OAuth Client
*AccountApi* | [**UpdateUser**](docs/AccountApi.md#updateuser) | **Put** /account/users/{username} | Update User
*AccountApi* | [**UpdateUserGrants**](docs/AccountApi.md#updateusergrants) | **Put** /account/users/{username}/grants | Update User&#39;s grants
*DomainsApi* | [**CloneDomain**](docs/DomainsApi.md#clonedomain) | **Post** /domains/{domainId}/clone | Clone Domain
*DomainsApi* | [**CreateDomain**](docs/DomainsApi.md#createdomain) | **Post** /domains | Create Domain
*DomainsApi* | [**CreateDomainRecord**](docs/DomainsApi.md#createdomainrecord) | **Post** /domains/{domainId}/records | Create Domain Record
*DomainsApi* | [**DeleteDomain**](docs/DomainsApi.md#deletedomain) | **Delete** /domains/{domainId} | Delete Domain
*DomainsApi* | [**DeleteDomainRecord**](docs/DomainsApi.md#deletedomainrecord) | **Delete** /domains/{domainId}/records/{recordId} | Delete Domain Record
*DomainsApi* | [**GetDomain**](docs/DomainsApi.md#getdomain) | **Get** /domains/{domainId} | View Domain
*DomainsApi* | [**GetDomainRecord**](docs/DomainsApi.md#getdomainrecord) | **Get** /domains/{domainId}/records/{recordId} | View Domain Record
*DomainsApi* | [**GetDomainRecords**](docs/DomainsApi.md#getdomainrecords) | **Get** /domains/{domainId}/records | List Domain Records
*DomainsApi* | [**GetDomains**](docs/DomainsApi.md#getdomains) | **Get** /domains | List Domains
*DomainsApi* | [**ImportDomain**](docs/DomainsApi.md#importdomain) | **Post** /domains/import | Import Domain
*DomainsApi* | [**UpdateDomain**](docs/DomainsApi.md#updatedomain) | **Put** /domains/{domainId} | Update Domain
*DomainsApi* | [**UpdateDomainRecord**](docs/DomainsApi.md#updatedomainrecord) | **Put** /domains/{domainId}/records/{recordId} | Update Domain Record
*ImagesApi* | [**CreateImage**](docs/ImagesApi.md#createimage) | **Post** /images | Create Image
*ImagesApi* | [**DeleteImage**](docs/ImagesApi.md#deleteimage) | **Delete** /images/{imageId} | Delete Image
*ImagesApi* | [**GetImage**](docs/ImagesApi.md#getimage) | **Get** /images/{imageId} | View Image
*ImagesApi* | [**GetImages**](docs/ImagesApi.md#getimages) | **Get** /images | List Images
*ImagesApi* | [**UpdateImage**](docs/ImagesApi.md#updateimage) | **Put** /images/{imageId} | Update Image
*LinodeInstancesApi* | [**AddLinodeConfig**](docs/LinodeInstancesApi.md#addlinodeconfig) | **Post** /linode/instances/{linodeId}/configs | Create Configuration Profile
*LinodeInstancesApi* | [**AddLinodeDisk**](docs/LinodeInstancesApi.md#addlinodedisk) | **Post** /linode/instances/{linodeId}/disks | Create Disk
*LinodeInstancesApi* | [**AddLinodeIP**](docs/LinodeInstancesApi.md#addlinodeip) | **Post** /linode/instances/{linodeId}/ips | Allocate IPv4 Address
*LinodeInstancesApi* | [**BootLinodeInstance**](docs/LinodeInstancesApi.md#bootlinodeinstance) | **Post** /linode/instances/{linodeId}/boot | Boot Linode
*LinodeInstancesApi* | [**CancelBackups**](docs/LinodeInstancesApi.md#cancelbackups) | **Post** /linode/instances/{linodeId}/backups/cancel | Cancel Backups
*LinodeInstancesApi* | [**CloneLinodeDisk**](docs/LinodeInstancesApi.md#clonelinodedisk) | **Post** /linode/instances/{linodeId}/disks/{diskId}/clone | Clone Disk
*LinodeInstancesApi* | [**CloneLinodeInstance**](docs/LinodeInstancesApi.md#clonelinodeinstance) | **Post** /linode/instances/{linodeId}/clone | Clone Linode
*LinodeInstancesApi* | [**CreateLinodeInstance**](docs/LinodeInstancesApi.md#createlinodeinstance) | **Post** /linode/instances | Create Linode
*LinodeInstancesApi* | [**CreateSnapshot**](docs/LinodeInstancesApi.md#createsnapshot) | **Post** /linode/instances/{linodeId}/backups | Create Snapshot
*LinodeInstancesApi* | [**DeleteDisk**](docs/LinodeInstancesApi.md#deletedisk) | **Delete** /linode/instances/{linodeId}/disks/{diskId} | Delete Disk
*LinodeInstancesApi* | [**DeleteLinodeConfig**](docs/LinodeInstancesApi.md#deletelinodeconfig) | **Delete** /linode/instances/{linodeId}/configs/{configId} | Delete Configuration Profile
*LinodeInstancesApi* | [**DeleteLinodeInstance**](docs/LinodeInstancesApi.md#deletelinodeinstance) | **Delete** /linode/instances/{linodeId} | Delete Linode
*LinodeInstancesApi* | [**EnableBackups**](docs/LinodeInstancesApi.md#enablebackups) | **Post** /linode/instances/{linodeId}/backups/enable | Enable Backups
*LinodeInstancesApi* | [**GetBackup**](docs/LinodeInstancesApi.md#getbackup) | **Get** /linode/instances/{linodeId}/backups/{backupId} | View Backup
*LinodeInstancesApi* | [**GetBackups**](docs/LinodeInstancesApi.md#getbackups) | **Get** /linode/instances/{linodeId}/backups | List Backups
*LinodeInstancesApi* | [**GetKernel**](docs/LinodeInstancesApi.md#getkernel) | **Get** /linode/kernels/{kernelId} | View Kernel
*LinodeInstancesApi* | [**GetKernels**](docs/LinodeInstancesApi.md#getkernels) | **Get** /linode/kernels | List Kernels
*LinodeInstancesApi* | [**GetLinodeConfig**](docs/LinodeInstancesApi.md#getlinodeconfig) | **Get** /linode/instances/{linodeId}/configs/{configId} | View Configuration Profile
*LinodeInstancesApi* | [**GetLinodeConfigs**](docs/LinodeInstancesApi.md#getlinodeconfigs) | **Get** /linode/instances/{linodeId}/configs | List Configuration Profiles
*LinodeInstancesApi* | [**GetLinodeDisk**](docs/LinodeInstancesApi.md#getlinodedisk) | **Get** /linode/instances/{linodeId}/disks/{diskId} | View Disk
*LinodeInstancesApi* | [**GetLinodeDisks**](docs/LinodeInstancesApi.md#getlinodedisks) | **Get** /linode/instances/{linodeId}/disks | List Disks
*LinodeInstancesApi* | [**GetLinodeIP**](docs/LinodeInstancesApi.md#getlinodeip) | **Get** /linode/instances/{linodeId}/ips/{address} | View IP Address
*LinodeInstancesApi* | [**GetLinodeIPs**](docs/LinodeInstancesApi.md#getlinodeips) | **Get** /linode/instances/{linodeId}/ips | List Networking Information
*LinodeInstancesApi* | [**GetLinodeInstance**](docs/LinodeInstancesApi.md#getlinodeinstance) | **Get** /linode/instances/{linodeId} | View Linode
*LinodeInstancesApi* | [**GetLinodeInstances**](docs/LinodeInstancesApi.md#getlinodeinstances) | **Get** /linode/instances | List Linodes
*LinodeInstancesApi* | [**GetLinodeStats**](docs/LinodeInstancesApi.md#getlinodestats) | **Get** /linode/instances/{linodeId}/stats | View Linode Statistics
*LinodeInstancesApi* | [**GetLinodeStatsByYearMonth**](docs/LinodeInstancesApi.md#getlinodestatsbyyearmonth) | **Get** /linode/instances/{linodeId}/stats/{year}/{month} | View Statistics (year/month)
*LinodeInstancesApi* | [**GetLinodeTransfer**](docs/LinodeInstancesApi.md#getlinodetransfer) | **Get** /linode/instances/{linodeId}/transfer | View Network Transfer
*LinodeInstancesApi* | [**GetLinodeVolumes**](docs/LinodeInstancesApi.md#getlinodevolumes) | **Get** /linode/instances/{linodeId}/volumes | List Linode&#39;s Volumes
*LinodeInstancesApi* | [**MigrateLinodeInstance**](docs/LinodeInstancesApi.md#migratelinodeinstance) | **Post** /linode/instances/{linodeId}/migrate | Initiate Pending Host Migration/DC Migration
*LinodeInstancesApi* | [**MutateLinodeInstance**](docs/LinodeInstancesApi.md#mutatelinodeinstance) | **Post** /linode/instances/{linodeId}/mutate | Upgrade Linode
*LinodeInstancesApi* | [**RebootLinodeInstance**](docs/LinodeInstancesApi.md#rebootlinodeinstance) | **Post** /linode/instances/{linodeId}/reboot | Reboot Linode
*LinodeInstancesApi* | [**RebuildLinodeInstance**](docs/LinodeInstancesApi.md#rebuildlinodeinstance) | **Post** /linode/instances/{linodeId}/rebuild | Rebuild Linode
*LinodeInstancesApi* | [**RemoveLinodeIP**](docs/LinodeInstancesApi.md#removelinodeip) | **Delete** /linode/instances/{linodeId}/ips/{address} | Delete IPv4 Address
*LinodeInstancesApi* | [**RescueLinodeInstance**](docs/LinodeInstancesApi.md#rescuelinodeinstance) | **Post** /linode/instances/{linodeId}/rescue | Boot Linode into Rescue Mode
*LinodeInstancesApi* | [**ResetDiskPassword**](docs/LinodeInstancesApi.md#resetdiskpassword) | **Post** /linode/instances/{linodeId}/disks/{diskId}/password | Reset Disk Root Password
*LinodeInstancesApi* | [**ResizeDisk**](docs/LinodeInstancesApi.md#resizedisk) | **Post** /linode/instances/{linodeId}/disks/{diskId}/resize | Resize Disk
*LinodeInstancesApi* | [**ResizeLinodeInstance**](docs/LinodeInstancesApi.md#resizelinodeinstance) | **Post** /linode/instances/{linodeId}/resize | Resize Linode
*LinodeInstancesApi* | [**RestoreBackup**](docs/LinodeInstancesApi.md#restorebackup) | **Post** /linode/instances/{linodeId}/backups/{backupId}/restore | Restore Backup
*LinodeInstancesApi* | [**ShutdownLinodeInstance**](docs/LinodeInstancesApi.md#shutdownlinodeinstance) | **Post** /linode/instances/{linodeId}/shutdown | Shut Down Linode
*LinodeInstancesApi* | [**UpdateDisk**](docs/LinodeInstancesApi.md#updatedisk) | **Put** /linode/instances/{linodeId}/disks/{diskId} | Update Disk
*LinodeInstancesApi* | [**UpdateLinodeConfig**](docs/LinodeInstancesApi.md#updatelinodeconfig) | **Put** /linode/instances/{linodeId}/configs/{configId} | Update Configuration Profile
*LinodeInstancesApi* | [**UpdateLinodeIP**](docs/LinodeInstancesApi.md#updatelinodeip) | **Put** /linode/instances/{linodeId}/ips/{address} | Update IP Address
*LinodeInstancesApi* | [**UpdateLinodeInstance**](docs/LinodeInstancesApi.md#updatelinodeinstance) | **Put** /linode/instances/{linodeId} | Update Linode
*LinodeKubernetesEngineLKEApi* | [**CreateLKECluster**](docs/LinodeKubernetesEngineLKEApi.md#createlkecluster) | **Post** /lke/clusters | Create Kubernetes Cluster
*LinodeKubernetesEngineLKEApi* | [**DeleteLKECluster**](docs/LinodeKubernetesEngineLKEApi.md#deletelkecluster) | **Delete** /lke/clusters/{clusterId} | Delete Kubernetes Cluster
*LinodeKubernetesEngineLKEApi* | [**DeleteLKENodePool**](docs/LinodeKubernetesEngineLKEApi.md#deletelkenodepool) | **Delete** /lke/clusters/{clusterId}/pools/{poolId} | Delete Node Pool
*LinodeKubernetesEngineLKEApi* | [**GetLKECluster**](docs/LinodeKubernetesEngineLKEApi.md#getlkecluster) | **Get** /lke/clusters/{clusterId} | View Kubernetes Cluster
*LinodeKubernetesEngineLKEApi* | [**GetLKEClusterAPIEndpoint**](docs/LinodeKubernetesEngineLKEApi.md#getlkeclusterapiendpoint) | **Get** /lke/clusters/{clusterId}/api-endpoint | View Kubernetes API Endpoint
*LinodeKubernetesEngineLKEApi* | [**GetLKEClusterKubeconfig**](docs/LinodeKubernetesEngineLKEApi.md#getlkeclusterkubeconfig) | **Get** /lke/clusters/{clusterId}/kubeconfig | View Kubeconfig
*LinodeKubernetesEngineLKEApi* | [**GetLKEClusterPools**](docs/LinodeKubernetesEngineLKEApi.md#getlkeclusterpools) | **Get** /lke/clusters/{clusterId}/pools | List Node Pools
*LinodeKubernetesEngineLKEApi* | [**GetLKEClusters**](docs/LinodeKubernetesEngineLKEApi.md#getlkeclusters) | **Get** /lke/clusters | List Kubernetes Clusters
*LinodeKubernetesEngineLKEApi* | [**GetLKENodePool**](docs/LinodeKubernetesEngineLKEApi.md#getlkenodepool) | **Get** /lke/clusters/{clusterId}/pools/{poolId} | View Node Pool
*LinodeKubernetesEngineLKEApi* | [**GetLKEVersion**](docs/LinodeKubernetesEngineLKEApi.md#getlkeversion) | **Get** /lke/versions/{version} | View Kubernetes Version
*LinodeKubernetesEngineLKEApi* | [**GetLKEVersions**](docs/LinodeKubernetesEngineLKEApi.md#getlkeversions) | **Get** /lke/versions | List Kubernetes Versions
*LinodeKubernetesEngineLKEApi* | [**PostLKEClusterPools**](docs/LinodeKubernetesEngineLKEApi.md#postlkeclusterpools) | **Post** /lke/clusters/{clusterId}/pools | Create Node Pool
*LinodeKubernetesEngineLKEApi* | [**PutLKECluster**](docs/LinodeKubernetesEngineLKEApi.md#putlkecluster) | **Put** /lke/clusters/{clusterId} | Update Kubernetes Cluster
*LinodeKubernetesEngineLKEApi* | [**PutLKENodePool**](docs/LinodeKubernetesEngineLKEApi.md#putlkenodepool) | **Put** /lke/clusters/{clusterId}/pools/{poolId} | Update Node Pool
*LinodeTypesApi* | [**GetLinodeType**](docs/LinodeTypesApi.md#getlinodetype) | **Get** /linode/types/{typeId} | View Type
*LinodeTypesApi* | [**GetLinodeTypes**](docs/LinodeTypesApi.md#getlinodetypes) | **Get** /linode/types | List Types
*LongviewApi* | [**CreateLongviewClient**](docs/LongviewApi.md#createlongviewclient) | **Post** /longview/clients | Create Longview Client
*LongviewApi* | [**DeleteLongviewClient**](docs/LongviewApi.md#deletelongviewclient) | **Delete** /longview/clients/{clientId} | Delete Longview Client
*LongviewApi* | [**GetLongviewClient**](docs/LongviewApi.md#getlongviewclient) | **Get** /longview/clients/{clientId} | View Longview Client
*LongviewApi* | [**GetLongviewClients**](docs/LongviewApi.md#getlongviewclients) | **Get** /longview/clients | List Longview Clients
*LongviewApi* | [**GetLongviewSubscription**](docs/LongviewApi.md#getlongviewsubscription) | **Get** /longview/subscriptions/{subscriptionId} | View Longview Subscription
*LongviewApi* | [**GetLongviewSubscriptions**](docs/LongviewApi.md#getlongviewsubscriptions) | **Get** /longview/subscriptions | List Longview Subscriptions
*LongviewApi* | [**UpdateLongviewClient**](docs/LongviewApi.md#updatelongviewclient) | **Put** /longview/clients/{clientId} | Update Longview Client
*ManagedApi* | [**CreateManagedContact**](docs/ManagedApi.md#createmanagedcontact) | **Post** /managed/contacts | Create Managed Contact
*ManagedApi* | [**CreateManagedCredential**](docs/ManagedApi.md#createmanagedcredential) | **Post** /managed/credentials | Create Managed Credential
*ManagedApi* | [**CreateManagedService**](docs/ManagedApi.md#createmanagedservice) | **Post** /managed/services | Create Managed Service
*ManagedApi* | [**DeleteManagedContact**](docs/ManagedApi.md#deletemanagedcontact) | **Delete** /managed/contacts/{contactId} | Delete Managed Contact
*ManagedApi* | [**DeleteManagedCredential**](docs/ManagedApi.md#deletemanagedcredential) | **Post** /managed/credentials/{credentialId}/revoke | Delete Managed Credential
*ManagedApi* | [**DeleteManagedService**](docs/ManagedApi.md#deletemanagedservice) | **Delete** /managed/services/{serviceId} | Delete Managed Service
*ManagedApi* | [**DisableManagedService**](docs/ManagedApi.md#disablemanagedservice) | **Post** /managed/services/{serviceId}/disable | Disable Managed Service
*ManagedApi* | [**EnableManagedService**](docs/ManagedApi.md#enablemanagedservice) | **Post** /managed/services/{serviceId}/enable | Enable Managed Service
*ManagedApi* | [**GetManagedContact**](docs/ManagedApi.md#getmanagedcontact) | **Get** /managed/contacts/{contactId} | View Managed Contact
*ManagedApi* | [**GetManagedContacts**](docs/ManagedApi.md#getmanagedcontacts) | **Get** /managed/contacts | List Managed Contacts
*ManagedApi* | [**GetManagedCredential**](docs/ManagedApi.md#getmanagedcredential) | **Get** /managed/credentials/{credentialId} | View Managed Credential
*ManagedApi* | [**GetManagedCredentials**](docs/ManagedApi.md#getmanagedcredentials) | **Get** /managed/credentials | List Managed Credentials
*ManagedApi* | [**GetManagedIssue**](docs/ManagedApi.md#getmanagedissue) | **Get** /managed/issues/{issueId} | View Managed Issue
*ManagedApi* | [**GetManagedIssues**](docs/ManagedApi.md#getmanagedissues) | **Get** /managed/issues | List Managed Issues
*ManagedApi* | [**GetManagedLinodeSetting**](docs/ManagedApi.md#getmanagedlinodesetting) | **Get** /managed/linode-settings/{linodeId} | View Linode&#39;s Managed Settings
*ManagedApi* | [**GetManagedLinodeSettings**](docs/ManagedApi.md#getmanagedlinodesettings) | **Get** /managed/linode-settings | List Managed Linode Settings
*ManagedApi* | [**GetManagedService**](docs/ManagedApi.md#getmanagedservice) | **Get** /managed/services/{serviceId} | View Managed Service
*ManagedApi* | [**GetManagedServices**](docs/ManagedApi.md#getmanagedservices) | **Get** /managed/services | List Managed Services
*ManagedApi* | [**GetManagedStats**](docs/ManagedApi.md#getmanagedstats) | **Get** /managed/stats | List Managed Stats
*ManagedApi* | [**UpdateManagedContact**](docs/ManagedApi.md#updatemanagedcontact) | **Put** /managed/contacts/{contactId} | Update Managed Contact
*ManagedApi* | [**UpdateManagedCredential**](docs/ManagedApi.md#updatemanagedcredential) | **Put** /managed/credentials/{credentialId} | Update Managed Credential
*ManagedApi* | [**UpdateManagedCredentialUsernamePassword**](docs/ManagedApi.md#updatemanagedcredentialusernamepassword) | **Post** /managed/credentials/{credentialId}/update | Update Managed Credential Username and Password
*ManagedApi* | [**UpdateManagedLinodeSetting**](docs/ManagedApi.md#updatemanagedlinodesetting) | **Put** /managed/linode-settings/{linodeId} | Update Linode&#39;s Managed Settings
*ManagedApi* | [**UpdateManagedService**](docs/ManagedApi.md#updatemanagedservice) | **Put** /managed/services/{serviceId} | Update Managed Service
*ManagedApi* | [**ViewManagedSSHKey**](docs/ManagedApi.md#viewmanagedsshkey) | **Get** /managed/credentials/sshkey | View Managed SSH Key
*NetworkingApi* | [**AllocateIP**](docs/NetworkingApi.md#allocateip) | **Post** /networking/ips | Allocate IP Address
*NetworkingApi* | [**AssignIPs**](docs/NetworkingApi.md#assignips) | **Post** /networking/ipv4/assign | Assign IPs to Linodes
*NetworkingApi* | [**GetIP**](docs/NetworkingApi.md#getip) | **Get** /networking/ips/{address} | View IP Address
*NetworkingApi* | [**GetIPs**](docs/NetworkingApi.md#getips) | **Get** /networking/ips | List IP Addresses
*NetworkingApi* | [**GetIPv6Pools**](docs/NetworkingApi.md#getipv6pools) | **Get** /networking/ipv6/pools | List IPv6 Pools
*NetworkingApi* | [**GetIPv6Ranges**](docs/NetworkingApi.md#getipv6ranges) | **Get** /networking/ipv6/ranges | List IPv6 Ranges
*NetworkingApi* | [**ShareIPs**](docs/NetworkingApi.md#shareips) | **Post** /networking/ipv4/share | Configure IP Sharing
*NetworkingApi* | [**UpdateIP**](docs/NetworkingApi.md#updateip) | **Put** /networking/ips/{address} | Update IP Address RDNS
*NodeBalancersApi* | [**CreateNodeBalancer**](docs/NodeBalancersApi.md#createnodebalancer) | **Post** /nodebalancers | Create NodeBalancer
*NodeBalancersApi* | [**CreateNodeBalancerConfig**](docs/NodeBalancersApi.md#createnodebalancerconfig) | **Post** /nodebalancers/{nodeBalancerId}/configs | Create Config
*NodeBalancersApi* | [**CreateNodeBalancerNode**](docs/NodeBalancersApi.md#createnodebalancernode) | **Post** /nodebalancers/{nodeBalancerId}/configs/{configId}/nodes | Create Node
*NodeBalancersApi* | [**DeleteNodeBalancer**](docs/NodeBalancersApi.md#deletenodebalancer) | **Delete** /nodebalancers/{nodeBalancerId} | Delete NodeBalancer
*NodeBalancersApi* | [**DeleteNodeBalancerConfig**](docs/NodeBalancersApi.md#deletenodebalancerconfig) | **Delete** /nodebalancers/{nodeBalancerId}/configs/{configId} | Delete Config
*NodeBalancersApi* | [**DeleteNodeBalancerConfigNode**](docs/NodeBalancersApi.md#deletenodebalancerconfignode) | **Delete** /nodebalancers/{nodeBalancerId}/configs/{configId}/nodes/{nodeId} | Delete Node
*NodeBalancersApi* | [**GetNodeBalancer**](docs/NodeBalancersApi.md#getnodebalancer) | **Get** /nodebalancers/{nodeBalancerId} | View NodeBalancer
*NodeBalancersApi* | [**GetNodeBalancerConfig**](docs/NodeBalancersApi.md#getnodebalancerconfig) | **Get** /nodebalancers/{nodeBalancerId}/configs/{configId} | View Config
*NodeBalancersApi* | [**GetNodeBalancerConfigNodes**](docs/NodeBalancersApi.md#getnodebalancerconfignodes) | **Get** /nodebalancers/{nodeBalancerId}/configs/{configId}/nodes | List Nodes
*NodeBalancersApi* | [**GetNodeBalancerConfigs**](docs/NodeBalancersApi.md#getnodebalancerconfigs) | **Get** /nodebalancers/{nodeBalancerId}/configs | List Configs
*NodeBalancersApi* | [**GetNodeBalancerNode**](docs/NodeBalancersApi.md#getnodebalancernode) | **Get** /nodebalancers/{nodeBalancerId}/configs/{configId}/nodes/{nodeId} | View Node
*NodeBalancersApi* | [**GetNodeBalancers**](docs/NodeBalancersApi.md#getnodebalancers) | **Get** /nodebalancers | List NodeBalancers
*NodeBalancersApi* | [**NodebalancersNodeBalancerIdStatsGet**](docs/NodeBalancersApi.md#nodebalancersnodebalanceridstatsget) | **Get** /nodebalancers/{nodeBalancerId}/stats | View NodeBalancer Statistics
*NodeBalancersApi* | [**RebuildNodeBalancerConfig**](docs/NodeBalancersApi.md#rebuildnodebalancerconfig) | **Post** /nodebalancers/{nodeBalancerId}/configs/{configId}/rebuild | Rebuild Config
*NodeBalancersApi* | [**UpdateNodeBalancer**](docs/NodeBalancersApi.md#updatenodebalancer) | **Put** /nodebalancers/{nodeBalancerId} | Update NodeBalancer
*NodeBalancersApi* | [**UpdateNodeBalancerConfig**](docs/NodeBalancersApi.md#updatenodebalancerconfig) | **Put** /nodebalancers/{nodeBalancerId}/configs/{configId} | Update Config
*NodeBalancersApi* | [**UpdateNodeBalancerNode**](docs/NodeBalancersApi.md#updatenodebalancernode) | **Put** /nodebalancers/{nodeBalancerId}/configs/{configId}/nodes/{nodeId} | Update Node
*ObjectStorageApi* | [**CancelObjectStorage**](docs/ObjectStorageApi.md#cancelobjectstorage) | **Post** /object-storage/cancel | Cancel Object Storage
*ObjectStorageApi* | [**CreateObjectStorageBucket**](docs/ObjectStorageApi.md#createobjectstoragebucket) | **Post** /object-storage/buckets | Create Object Storage Bucket
*ObjectStorageApi* | [**CreateObjectStorageKeys**](docs/ObjectStorageApi.md#createobjectstoragekeys) | **Post** /object-storage/keys | Create an Object Storage Key
*ObjectStorageApi* | [**CreateObjectStorageObjectURL**](docs/ObjectStorageApi.md#createobjectstorageobjecturl) | **Post** /object-storage/buckets/{clusterId}/{bucket}/object-url | Create Object Storage Object URL
*ObjectStorageApi* | [**DeleteObjectStorageBucket**](docs/ObjectStorageApi.md#deleteobjectstoragebucket) | **Delete** /object-storage/buckets/{clusterId}/{bucket} | Remove Object Storage Bucket
*ObjectStorageApi* | [**DeleteObjectStorageKey**](docs/ObjectStorageApi.md#deleteobjectstoragekey) | **Delete** /object-storage/keys/{keyId} | Revoke Object Storage Key
*ObjectStorageApi* | [**GetObjectStorageBucket**](docs/ObjectStorageApi.md#getobjectstoragebucket) | **Get** /object-storage/buckets/{clusterId}/{bucket} | View Object Storage Bucket
*ObjectStorageApi* | [**GetObjectStorageBucketContent**](docs/ObjectStorageApi.md#getobjectstoragebucketcontent) | **Get** /object-storage/buckets/{clusterId}/{bucket}/object-list | List Object Storage Bucket Contents
*ObjectStorageApi* | [**GetObjectStorageBucketinCluster**](docs/ObjectStorageApi.md#getobjectstoragebucketincluster) | **Get** /object-storage/buckets/{clusterId} | List Object Storage Buckets in Cluster
*ObjectStorageApi* | [**GetObjectStorageBuckets**](docs/ObjectStorageApi.md#getobjectstoragebuckets) | **Get** /object-storage/buckets | List Object Storage Buckets
*ObjectStorageApi* | [**GetObjectStorageCluster**](docs/ObjectStorageApi.md#getobjectstoragecluster) | **Get** /object-storage/clusters/{clusterId} | View Cluster
*ObjectStorageApi* | [**GetObjectStorageClusters**](docs/ObjectStorageApi.md#getobjectstorageclusters) | **Get** /object-storage/clusters | List Clusters
*ObjectStorageApi* | [**GetObjectStorageKey**](docs/ObjectStorageApi.md#getobjectstoragekey) | **Get** /object-storage/keys/{keyId} | View Object Storage Key
*ObjectStorageApi* | [**GetObjectStorageKeys**](docs/ObjectStorageApi.md#getobjectstoragekeys) | **Get** /object-storage/keys | List Object Storage Keys
*ObjectStorageApi* | [**ModifyObjectStorageBucketAccess**](docs/ObjectStorageApi.md#modifyobjectstoragebucketaccess) | **Post** /object-storage/buckets/{clusterId}/{bucket}/access | Modify Object Storage Bucket Access
*ObjectStorageApi* | [**UpdateObjectStorageKey**](docs/ObjectStorageApi.md#updateobjectstoragekey) | **Put** /object-storage/keys/{keyId} | Update an Object Storage Key
*ProfileApi* | [**AddSSHKey**](docs/ProfileApi.md#addsshkey) | **Post** /profile/sshkeys | Add SSH Key
*ProfileApi* | [**CreatePersonalAccessToken**](docs/ProfileApi.md#createpersonalaccesstoken) | **Post** /profile/tokens | Create Personal Access Token
*ProfileApi* | [**DeletePersonalAccessToken**](docs/ProfileApi.md#deletepersonalaccesstoken) | **Delete** /profile/tokens/{tokenId} | Revoke Personal Access Token
*ProfileApi* | [**DeleteProfileApp**](docs/ProfileApi.md#deleteprofileapp) | **Delete** /profile/apps/{appId} | Revoke App Access
*ProfileApi* | [**DeleteSSHKey**](docs/ProfileApi.md#deletesshkey) | **Delete** /profile/sshkeys/{sshKeyId} | Delete SSH Key
*ProfileApi* | [**GetDevices**](docs/ProfileApi.md#getdevices) | **Get** /profile/devices | List Trusted Devices
*ProfileApi* | [**GetPersonalAccessToken**](docs/ProfileApi.md#getpersonalaccesstoken) | **Get** /profile/tokens/{tokenId} | View Personal Access Token
*ProfileApi* | [**GetPersonalAccessTokens**](docs/ProfileApi.md#getpersonalaccesstokens) | **Get** /profile/tokens | List Personal Access Tokens
*ProfileApi* | [**GetProfile**](docs/ProfileApi.md#getprofile) | **Get** /profile | View Profile
*ProfileApi* | [**GetProfileApp**](docs/ProfileApi.md#getprofileapp) | **Get** /profile/apps/{appId} | View Authorized App
*ProfileApi* | [**GetProfileApps**](docs/ProfileApi.md#getprofileapps) | **Get** /profile/apps | List Authorized Apps
*ProfileApi* | [**GetProfileGrants**](docs/ProfileApi.md#getprofilegrants) | **Get** /profile/grants | List Grants
*ProfileApi* | [**GetSSHKey**](docs/ProfileApi.md#getsshkey) | **Get** /profile/sshkeys/{sshKeyId} | View SSH Key
*ProfileApi* | [**GetSSHKeys**](docs/ProfileApi.md#getsshkeys) | **Get** /profile/sshkeys | List SSH Keys
*ProfileApi* | [**GetTrustedDevice**](docs/ProfileApi.md#gettrusteddevice) | **Get** /profile/devices/{deviceId} | View Trusted Device
*ProfileApi* | [**GetUserPreferences**](docs/ProfileApi.md#getuserpreferences) | **Get** /profile/preferences | View User Preferences
*ProfileApi* | [**RevokeTrustedDevice**](docs/ProfileApi.md#revoketrusteddevice) | **Delete** /profile/devices/{deviceId} | Revoke Trusted Device
*ProfileApi* | [**TfaConfirm**](docs/ProfileApi.md#tfaconfirm) | **Post** /profile/tfa-enable-confirm | Confirm/Enable Two Factor Authentication
*ProfileApi* | [**TfaDisable**](docs/ProfileApi.md#tfadisable) | **Post** /profile/tfa-disable | Disable Two Factor Authentication
*ProfileApi* | [**TfaEnable**](docs/ProfileApi.md#tfaenable) | **Post** /profile/tfa-enable | Create Two Factor Secret
*ProfileApi* | [**UpdatePersonalAccessToken**](docs/ProfileApi.md#updatepersonalaccesstoken) | **Put** /profile/tokens/{tokenId} | Update Personal Access Token
*ProfileApi* | [**UpdateProfile**](docs/ProfileApi.md#updateprofile) | **Put** /profile | Update Profile
*ProfileApi* | [**UpdateSSHKey**](docs/ProfileApi.md#updatesshkey) | **Put** /profile/sshkeys/{sshKeyId} | Update SSH Key
*ProfileApi* | [**UpdateUserPreferences**](docs/ProfileApi.md#updateuserpreferences) | **Put** /profile/preferences | Update User Preferences
*RegionsApi* | [**GetRegion**](docs/RegionsApi.md#getregion) | **Get** /regions/{regionId} | View Region
*RegionsApi* | [**GetRegions**](docs/RegionsApi.md#getregions) | **Get** /regions | List Regions
*StackScriptsApi* | [**AddStackScript**](docs/StackScriptsApi.md#addstackscript) | **Post** /linode/stackscripts | Create StackScript
*StackScriptsApi* | [**DeleteStackScript**](docs/StackScriptsApi.md#deletestackscript) | **Delete** /linode/stackscripts/{stackscriptId} | Delete StackScript
*StackScriptsApi* | [**GetStackScript**](docs/StackScriptsApi.md#getstackscript) | **Get** /linode/stackscripts/{stackscriptId} | View StackScript
*StackScriptsApi* | [**GetStackScripts**](docs/StackScriptsApi.md#getstackscripts) | **Get** /linode/stackscripts | List StackScripts
*StackScriptsApi* | [**UpdateStackScript**](docs/StackScriptsApi.md#updatestackscript) | **Put** /linode/stackscripts/{stackscriptId} | Update StackScript
*SupportApi* | [**CloseTicket**](docs/SupportApi.md#closeticket) | **Post** /support/tickets/{ticketId}/close | Close Support Ticket
*SupportApi* | [**CreateTicket**](docs/SupportApi.md#createticket) | **Post** /support/tickets | Open Support Ticket
*SupportApi* | [**CreateTicketAttachment**](docs/SupportApi.md#createticketattachment) | **Post** /support/tickets/{ticketId}/attachments | Create Ticket Attachment
*SupportApi* | [**CreateTicketReply**](docs/SupportApi.md#createticketreply) | **Post** /support/tickets/{ticketId}/replies | Create Reply
*SupportApi* | [**GetTicket**](docs/SupportApi.md#getticket) | **Get** /support/tickets/{ticketId} | View Support Ticket
*SupportApi* | [**GetTicketReplies**](docs/SupportApi.md#getticketreplies) | **Get** /support/tickets/{ticketId}/replies | List Replies
*SupportApi* | [**GetTickets**](docs/SupportApi.md#gettickets) | **Get** /support/tickets | List Support Tickets
*TagsApi* | [**CreateTag**](docs/TagsApi.md#createtag) | **Post** /tags | Create New Tag
*TagsApi* | [**DeleteTag**](docs/TagsApi.md#deletetag) | **Delete** /tags/{label} | Delete a Tag
*TagsApi* | [**GetTaggedObjects**](docs/TagsApi.md#gettaggedobjects) | **Get** /tags/{label} | List Tagged Objects
*TagsApi* | [**GetTags**](docs/TagsApi.md#gettags) | **Get** /tags | List Tags
*VolumesApi* | [**AttachVolume**](docs/VolumesApi.md#attachvolume) | **Post** /volumes/{volumeId}/attach | Attach Volume
*VolumesApi* | [**CloneVolume**](docs/VolumesApi.md#clonevolume) | **Post** /volumes/{volumeId}/clone | Clone Volume
*VolumesApi* | [**CreateVolume**](docs/VolumesApi.md#createvolume) | **Post** /volumes | Create Volume
*VolumesApi* | [**DeleteVolume**](docs/VolumesApi.md#deletevolume) | **Delete** /volumes/{volumeId} | Delete Volume
*VolumesApi* | [**DetachVolume**](docs/VolumesApi.md#detachvolume) | **Post** /volumes/{volumeId}/detach | Detach Volume
*VolumesApi* | [**GetVolume**](docs/VolumesApi.md#getvolume) | **Get** /volumes/{volumeId} | View Volume
*VolumesApi* | [**GetVolumes**](docs/VolumesApi.md#getvolumes) | **Get** /volumes | List Volumes
*VolumesApi* | [**ResizeVolume**](docs/VolumesApi.md#resizevolume) | **Post** /volumes/{volumeId}/resize | Resize Volume
*VolumesApi* | [**UpdateVolume**](docs/VolumesApi.md#updatevolume) | **Put** /volumes/{volumeId} | Update Volume


## Documentation For Models

 - [Account](docs/Account.md)
 - [AccountActivePromotions](docs/AccountActivePromotions.md)
 - [AccountCreditCard](docs/AccountCreditCard.md)
 - [AccountSettings](docs/AccountSettings.md)
 - [AuthorizedApp](docs/AuthorizedApp.md)
 - [Backup](docs/Backup.md)
 - [BackupDisks](docs/BackupDisks.md)
 - [CreditCard](docs/CreditCard.md)
 - [Device](docs/Device.md)
 - [Devices](docs/Devices.md)
 - [Disk](docs/Disk.md)
 - [DiskRequest](docs/DiskRequest.md)
 - [Domain](docs/Domain.md)
 - [DomainRecord](docs/DomainRecord.md)
 - [ErrorObject](docs/ErrorObject.md)
 - [Event](docs/Event.md)
 - [EventEntity](docs/EventEntity.md)
 - [EventSecondaryEntity](docs/EventSecondaryEntity.md)
 - [Grant](docs/Grant.md)
 - [GrantsResponse](docs/GrantsResponse.md)
 - [GrantsResponseGlobal](docs/GrantsResponseGlobal.md)
 - [IPv6Pool](docs/IPv6Pool.md)
 - [IPv6Range](docs/IPv6Range.md)
 - [ImagePrivate](docs/ImagePrivate.md)
 - [ImagePublic](docs/ImagePublic.md)
 - [InlineObject](docs/InlineObject.md)
 - [InlineObject1](docs/InlineObject1.md)
 - [InlineObject10](docs/InlineObject10.md)
 - [InlineObject11](docs/InlineObject11.md)
 - [InlineObject12](docs/InlineObject12.md)
 - [InlineObject13](docs/InlineObject13.md)
 - [InlineObject14](docs/InlineObject14.md)
 - [InlineObject15](docs/InlineObject15.md)
 - [InlineObject2](docs/InlineObject2.md)
 - [InlineObject3](docs/InlineObject3.md)
 - [InlineObject4](docs/InlineObject4.md)
 - [InlineObject5](docs/InlineObject5.md)
 - [InlineObject6](docs/InlineObject6.md)
 - [InlineObject7](docs/InlineObject7.md)
 - [InlineObject8](docs/InlineObject8.md)
 - [InlineObject9](docs/InlineObject9.md)
 - [InlineResponse200](docs/InlineResponse200.md)
 - [InlineResponse2001](docs/InlineResponse2001.md)
 - [InlineResponse20010](docs/InlineResponse20010.md)
 - [InlineResponse20011](docs/InlineResponse20011.md)
 - [InlineResponse20012](docs/InlineResponse20012.md)
 - [InlineResponse20013](docs/InlineResponse20013.md)
 - [InlineResponse20013Snapshot](docs/InlineResponse20013Snapshot.md)
 - [InlineResponse20014](docs/InlineResponse20014.md)
 - [InlineResponse20015](docs/InlineResponse20015.md)
 - [InlineResponse20016](docs/InlineResponse20016.md)
 - [InlineResponse20017](docs/InlineResponse20017.md)
 - [InlineResponse20018](docs/InlineResponse20018.md)
 - [InlineResponse20019](docs/InlineResponse20019.md)
 - [InlineResponse2002](docs/InlineResponse2002.md)
 - [InlineResponse20020](docs/InlineResponse20020.md)
 - [InlineResponse20021](docs/InlineResponse20021.md)
 - [InlineResponse20022](docs/InlineResponse20022.md)
 - [InlineResponse20023](docs/InlineResponse20023.md)
 - [InlineResponse20024](docs/InlineResponse20024.md)
 - [InlineResponse20025](docs/InlineResponse20025.md)
 - [InlineResponse20026](docs/InlineResponse20026.md)
 - [InlineResponse20027](docs/InlineResponse20027.md)
 - [InlineResponse20028](docs/InlineResponse20028.md)
 - [InlineResponse20029](docs/InlineResponse20029.md)
 - [InlineResponse2003](docs/InlineResponse2003.md)
 - [InlineResponse20030](docs/InlineResponse20030.md)
 - [InlineResponse20031](docs/InlineResponse20031.md)
 - [InlineResponse20032](docs/InlineResponse20032.md)
 - [InlineResponse20033](docs/InlineResponse20033.md)
 - [InlineResponse20034](docs/InlineResponse20034.md)
 - [InlineResponse20035](docs/InlineResponse20035.md)
 - [InlineResponse20036](docs/InlineResponse20036.md)
 - [InlineResponse20037](docs/InlineResponse20037.md)
 - [InlineResponse20038](docs/InlineResponse20038.md)
 - [InlineResponse20039](docs/InlineResponse20039.md)
 - [InlineResponse2004](docs/InlineResponse2004.md)
 - [InlineResponse20040](docs/InlineResponse20040.md)
 - [InlineResponse20041](docs/InlineResponse20041.md)
 - [InlineResponse20042](docs/InlineResponse20042.md)
 - [InlineResponse20043](docs/InlineResponse20043.md)
 - [InlineResponse20044](docs/InlineResponse20044.md)
 - [InlineResponse20045](docs/InlineResponse20045.md)
 - [InlineResponse20046](docs/InlineResponse20046.md)
 - [InlineResponse20047](docs/InlineResponse20047.md)
 - [InlineResponse20048](docs/InlineResponse20048.md)
 - [InlineResponse20049](docs/InlineResponse20049.md)
 - [InlineResponse2005](docs/InlineResponse2005.md)
 - [InlineResponse20050](docs/InlineResponse20050.md)
 - [InlineResponse2006](docs/InlineResponse2006.md)
 - [InlineResponse2007](docs/InlineResponse2007.md)
 - [InlineResponse2008](docs/InlineResponse2008.md)
 - [InlineResponse2009](docs/InlineResponse2009.md)
 - [InlineResponse409](docs/InlineResponse409.md)
 - [InlineResponse409Errors](docs/InlineResponse409Errors.md)
 - [InlineResponseDefault](docs/InlineResponseDefault.md)
 - [Invoice](docs/Invoice.md)
 - [InvoiceItem](docs/InvoiceItem.md)
 - [IpAddress](docs/IpAddress.md)
 - [IpAddressPrivate](docs/IpAddressPrivate.md)
 - [IpAddressV6LinkLocal](docs/IpAddressV6LinkLocal.md)
 - [IpAddressV6Slaac](docs/IpAddressV6Slaac.md)
 - [Kernel](docs/Kernel.md)
 - [Linode](docs/Linode.md)
 - [LinodeBase](docs/LinodeBase.md)
 - [LinodeConfig](docs/LinodeConfig.md)
 - [LinodeConfigHelpers](docs/LinodeConfigHelpers.md)
 - [LinodeRequest](docs/LinodeRequest.md)
 - [LinodeStats](docs/LinodeStats.md)
 - [LinodeStatsIo](docs/LinodeStatsIo.md)
 - [LinodeStatsNetv4](docs/LinodeStatsNetv4.md)
 - [LinodeStatsNetv6](docs/LinodeStatsNetv6.md)
 - [LinodeType](docs/LinodeType.md)
 - [LinodeTypeAddons](docs/LinodeTypeAddons.md)
 - [LinodeTypeAddonsBackups](docs/LinodeTypeAddonsBackups.md)
 - [LinodeTypeAddonsBackupsPrice](docs/LinodeTypeAddonsBackupsPrice.md)
 - [LinodeTypePrice](docs/LinodeTypePrice.md)
 - [LkeCluster](docs/LkeCluster.md)
 - [LkeClusterRequestBody](docs/LkeClusterRequestBody.md)
 - [LkeNodePool](docs/LkeNodePool.md)
 - [LkeNodePoolRequestBody](docs/LkeNodePoolRequestBody.md)
 - [LkeNodeStatus](docs/LkeNodeStatus.md)
 - [LkeVersion](docs/LkeVersion.md)
 - [LongviewClient](docs/LongviewClient.md)
 - [LongviewClientApps](docs/LongviewClientApps.md)
 - [LongviewSubscription](docs/LongviewSubscription.md)
 - [LongviewSubscriptionPrice](docs/LongviewSubscriptionPrice.md)
 - [ManagedContact](docs/ManagedContact.md)
 - [ManagedContactPhone](docs/ManagedContactPhone.md)
 - [ManagedCredential](docs/ManagedCredential.md)
 - [ManagedIssue](docs/ManagedIssue.md)
 - [ManagedIssueEntity](docs/ManagedIssueEntity.md)
 - [ManagedLinodeSettings](docs/ManagedLinodeSettings.md)
 - [ManagedLinodeSettingsSsh](docs/ManagedLinodeSettingsSsh.md)
 - [ManagedService](docs/ManagedService.md)
 - [NodeBalancer](docs/NodeBalancer.md)
 - [NodeBalancerConfig](docs/NodeBalancerConfig.md)
 - [NodeBalancerConfigNodesStatus](docs/NodeBalancerConfigNodesStatus.md)
 - [NodeBalancerNode](docs/NodeBalancerNode.md)
 - [NodeBalancerStats](docs/NodeBalancerStats.md)
 - [NodeBalancerStatsData](docs/NodeBalancerStatsData.md)
 - [NodeBalancerStatsDataTraffic](docs/NodeBalancerStatsDataTraffic.md)
 - [NodeBalancerTransfer](docs/NodeBalancerTransfer.md)
 - [Notification](docs/Notification.md)
 - [NotificationEntity](docs/NotificationEntity.md)
 - [OAuthClient](docs/OAuthClient.md)
 - [ObjectStorageBucket](docs/ObjectStorageBucket.md)
 - [ObjectStorageCluster](docs/ObjectStorageCluster.md)
 - [ObjectStorageKey](docs/ObjectStorageKey.md)
 - [ObjectStorageObject](docs/ObjectStorageObject.md)
 - [PaginationEnvelope](docs/PaginationEnvelope.md)
 - [PayPal](docs/PayPal.md)
 - [PayPalExecute](docs/PayPalExecute.md)
 - [Payment](docs/Payment.md)
 - [PaymentRequest](docs/PaymentRequest.md)
 - [PersonalAccessToken](docs/PersonalAccessToken.md)
 - [Profile](docs/Profile.md)
 - [ProfileReferrals](docs/ProfileReferrals.md)
 - [Region](docs/Region.md)
 - [RescueDevices](docs/RescueDevices.md)
 - [SshKey](docs/SshKey.md)
 - [SshKeyRequest](docs/SshKeyRequest.md)
 - [StackScript](docs/StackScript.md)
 - [StatsData](docs/StatsData.md)
 - [StatsDataAvailable](docs/StatsDataAvailable.md)
 - [SupportTicket](docs/SupportTicket.md)
 - [SupportTicketEntity](docs/SupportTicketEntity.md)
 - [SupportTicketReply](docs/SupportTicketReply.md)
 - [SupportTicketRequest](docs/SupportTicketRequest.md)
 - [Tag](docs/Tag.md)
 - [Transfer](docs/Transfer.md)
 - [TrustedDevice](docs/TrustedDevice.md)
 - [User](docs/User.md)
 - [UserDefinedField](docs/UserDefinedField.md)
 - [Volume](docs/Volume.md)


## Documentation For Authorization



## oauth


- **Type**: OAuth
- **Flow**: accessCode
- **Authorization URL**: https://login.linode.com/oauth/authorize
- **Scopes**: 
 - **account:read_only**: Allows access to GET information about your Account.
 - **account:read_write**: Allows access to all endpoints related to your Account.
 - **domains:read_only**: Allows access to GET Domains on your Account.
 - **domains:read_write**: Allows access to all Domain endpoints.
 - **events:read_only**: Allows access to GET your Events.
 - **events:read_write**: Allows access to all endpoints related to your Events.
 - **images:read_only**: Allows access to GET your Images.
 - **images:read_write**: Allows access to all endpoints related to your Images.
 - **ips:read_only**: Allows access to GET your ips.
 - **ips:read_write**: Allows access to all endpoints related to your ips.
 - **linodes:read_only**: Allows access to GET Linodes on your Account.
 - **linodes:read_write**: Allow access to all endpoints related to your Linodes.
 - **lke:read_only**: Allows access to GET LKE Clusters on your Account.
 - **lke:read_write**: Allows access to all endpoints related to LKE Clusters on your Account.
 - **longview:read_only**: Allows access to GET your Longview Clients.
 - **longview:read_write**: Allows access to all endpoints related to your Longview Clients.
 - **nodebalancers:read_only**: Allows access to GET NodeBalancers on your Account.
 - **nodebalancers:read_write**: Allows access to all NodeBalancer endpoints.
 - **stackscripts:read_only**: Allows access to GET your StackScripts.
 - **stackscripts:read_write**: Allows access to all endpoints related to your StackScripts.
 - **volumes:read_only**: Allows access to GET your Volumes.
 - **volumes:read_write**: Allows access to all endpoints related to your Volumes.

Example

```golang
auth := context.WithValue(context.Background(), sw.ContextAccessToken, "ACCESSTOKENSTRING")
r, err := client.Service.Operation(auth, args)
```

Or via OAuth2 module to automatically refresh tokens and perform user authentication.

```golang
import "golang.org/x/oauth2"

/* Perform OAuth2 round trip request and obtain a token */

tokenSource := oauth2cfg.TokenSource(createContext(httpClient), &token)
auth := context.WithValue(oauth2.NoContext, sw.ContextOAuth2, tokenSource)
r, err := client.Service.Operation(auth, args)
```


## personalAccessToken

- **Type**: HTTP basic authentication

Example

```golang
auth := context.WithValue(context.Background(), sw.ContextBasicAuth, sw.BasicAuth{
    UserName: "username",
    Password: "password",
})
r, err := client.Service.Operation(auth, args)
```



## Author



