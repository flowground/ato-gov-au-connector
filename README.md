# ![LOGO](logo.png) Business Registries **flow**ground Connector

## Description

A generated **flow**ground connector for the Business Registries API (version 0.0.6).

Generated from: https://api.apis.guru/v2/specs/ato.gov.au/0.0.6/swagger.json<br/>
Generated at: 2019-05-07T17:37:02+03:00

## API Description

# Introduction
The Business Registries API is built on HTTP. The API is RESTful. It has predictable resource URIs.

  The API is documented in <a target="_blank" href="https://github.com/OAI/OpenAPI-Specification">OpenAPI</a> format.
  In addition to the standard OpenAPI syntax we use a few
  <a target="_blank" href="https://github.com/Rebilly/ReDoc/blob/master/docs/redoc-vendor-extensions.md">vendor extensions</a>.

# Overview
The following sections describe the resources that make up the Business Registries REST API.
## Current Version
By default, all requests to https://api.abr.ato.gov.au receive the `v1` version of the REST API. We encourage you to explicitly request this version via the `Accept` header.

    Accept: application/vnd.abr-ato.v1+json

## Schema
All API access is over HTTPS, and accessed from https://api.abr.ato.gov.au. All data is sent and received as JSON. Blank fields are included.

  All dates use the [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format:

    YYYY-MM-DD

  For example: `2017-07-01` (the 1st of July 2017)

  All timestamps use the [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format:

    YYYY-MM-DDTHH:MM:SSZ

  For example: `2017-07-01T11:05:06+10:00`

## Timezones
Some requests allow for specifying timestamps or generate timestamps with time zone information. We apply the following rules, in order of priority, to determine timezone information for API calls.
### Explicitly provide an ISO 8601 timestamp with timezone information
For API calls that allow for a timestamp to be specified, we use that exact timestamp.

  For example: `2017-07-01T11:05:06+10:00`

## Pagination
Information about pagination is provided in the [Link](https://tools.ietf.org/html/rfc5988#page-6) header.

  For example:

    Link: <https://api.abr.ato.gov.au/individuals?page=2>; rel="next",
          <https://api.abr.ato.gov.au/individuals?page=34>; rel="last"

`rel="next"` states that the next page is `page=2`. This makes sense, since by default, all paginated queries start at page `1`. `rel="last"` provides some more information, stating that the last page of results is on `page 34`. Accordingly, we have 33 more pages of information that we can consume.
## Parameters
Many API methods take optional parameters:

    GET /individuals/1234/addresses/?addressType='Mailing'

In this example, the '1234' value is provided for the `:partyId` parameter in the path while `:addressType` is passed in the query string.
For POST, PATCH, PUT, and DELETE requests, parameters not included in the URL should be encoded as JSON with a Content-Type of 'application/json'.
## Metadata
The API provides **metadata services** that you can use to discover information about the classifcation schemes and values used by the Registry.

  For example:

    GET /classifications/roles

  Sample response:

    [
      {
        "id": "123e4567-e89b-12d3-a456-426655440001",
        "role": "Director",
        "roleDescription": "An individual responsible for managing a company's ...",
        "relationship": "Directorship",
        "reciprocalRole": "Company",
        "reciprocalRoleDescription": "An incorporated legal entity."
      },
      {
        ...
      }
    ]

## Root Endpoint
You can issue a GET request to the root endpoint (also known as the service root) to get all the endpoint categories that the REST API supports:

    curl https://api.abr.ato.gov.au

## Authentication
The Business Registries API supports API Key authentication.

  When you sign up for an account, you are given your first API key. You can generate additional API keys, and delete
  API keys (as you may need to rotate your keys in the future). You authenticate to the Business Registries API by
  providing your secret key in the request header.

  **Note:** Some requests will return `404 Not Found`, instead of `403 Permission Denied`. This is to prevent the
  accidental leakage of information to unauthorised users.


## Authorization

This API does not require authorization.

## Actions

### Retrieve a list of business names

> Retrieve a list of business names

*Tags:* `Business Names`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of address types

*Tags:* `Address Types`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of business name lifecycle states

*Tags:* `Business Name Lifecycle States`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of electronic address types

*Tags:* `Electronic Address Types`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of genders

*Tags:* `Genders`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of legal entity types

*Tags:* `Legal Entity Types`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of license lifecycle states

*Tags:* `License Lifecycle States`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of license types

*Tags:* `License Types`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of name directions

*Tags:* `Name Directions`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of name prefixes

*Tags:* `Name Prefixes`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of name types

*Tags:* `Name Types`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of registered identifier types

*Tags:* `Registered Identifier Types`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of roles

*Tags:* `Roles`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of individuals

> Retrieve a list of individuals

*Tags:* `Individuals`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `dateOfBirth` - _optional_ - The individual's date of birth, for example, `1979-01-13` (in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format).
* `placeOfBirth` - _optional_ - The individual's place of birth, for example, `Tamworth`.

### Create an individual

> Create an individual

*Tags:* `Individuals`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Delete an individual

> Delete an individual with the specified identifier

*Tags:* `Individuals`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Retrieve an individual

> Retrieve an individual with the specified identifier

*Tags:* `Individuals`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Update an individual

> Update an individual

*Tags:* `Individuals`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Retrieve a list of addresses

*Tags:* `Individuals Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Create an address

> Create an address

*Tags:* `Individuals Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Delete an address

> Delete an address

*Tags:* `Individuals Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Retrieve an address

> Retrieve an address

*Tags:* `Individuals Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Update an address

> Update an address

*Tags:* `Individuals Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Retrieve a list of business names

*Tags:* `Individuals Business Names`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Create a business name

> Create a business name

*Tags:* `Individuals Business Names`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Delete a business name

> Delete a business name

*Tags:* `Individuals Business Names`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Retrieve a business name

> Retrieve a business name

*Tags:* `Individuals Business Names`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Update a business name

> Update a business name

*Tags:* `Individuals Business Names`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Retrieve a list of electronic addresses

*Tags:* `Individuals Electronic Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Create an electronic address

> Create an electronic address

*Tags:* `Individuals Electronic Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Delete an electronic address

> Delete an electronic address

*Tags:* `Individuals Electronic Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Retrieve an electronic address

> Retrieve an electronic address

*Tags:* `Individuals Electronic Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Update an electronic address

> Update an electronic address

*Tags:* `Individuals Electronic Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Retrieve a list of licenses

*Tags:* `Individuals Licenses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Create a license

> Create a license

*Tags:* `Individuals Licenses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Delete a license

> Delete a license

*Tags:* `Individuals Licenses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Retrieve a license

> Retrieve a license

*Tags:* `Individuals Licenses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Update a license

> Update a license

*Tags:* `Individuals Licenses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Retrieve a list of roles

*Tags:* `Individuals Roles`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Create a role

> Create a role

*Tags:* `Individuals Roles`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Delete a role

> Delete a role

*Tags:* `Individuals Roles`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `roleId` - _required_ - The role identifier.

### Retrieve a role

> Retrieve a role

*Tags:* `Individuals Roles`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `roleId` - _required_ - The role identifier.

### Update a role

> Update a role

*Tags:* `Individuals Roles`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `roleId` - _required_ - The role identifier.

### Retrieve a list of licenses

> Retrieve a list of licenses

*Tags:* `Licenses`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Retrieve a list of organisations

> Retrieve a list of organisations

*Tags:* `Organisations`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `registeredIdentifier` - _optional_ - The registered identifier, for example, `ACN` or `ABN`.
* `identifier` - _optional_ - The identifier, for example, `123456789`.

### Create an organisation

> Create an organisation

*Tags:* `Organisations`

#### Input Parameters
* `apiKey` - _required_ - The API key.

### Delete an organisation

> Delete an organisation with the specified identifier

*Tags:* `Organisations`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Retrieve an organisation

> Retrieve an organisation with the specified identifier

*Tags:* `Organisations`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Update an organisation

> Update an organisation

*Tags:* `Organisations`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Retrieve a list of addresses

*Tags:* `Organisations Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Create an address

> Create an address

*Tags:* `Organisations Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Delete an address

> Delete an address

*Tags:* `Organisations Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Retrieve an address

> Retrieve an address

*Tags:* `Organisations Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Update an address

> Update an address

*Tags:* `Organisations Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Retrieve a list of business names

*Tags:* `Organisations Business Names`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Create a business name

> Create a business name

*Tags:* `Organisations Business Names`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Delete a business name

> Delete a business name

*Tags:* `Organisations Business Names`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Retrieve a business name

> Retrieve a business name

*Tags:* `Organisations Business Names`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Update a business name

> Update a business name

*Tags:* `Organisations Business Names`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Retrieve a list of electronic addresses

*Tags:* `Organisations Electronic Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Create an electronic address

> Create an electronic address

*Tags:* `Organisations Electronic Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Delete an electronic address

> Delete an electronic address

*Tags:* `Organisations Electronic Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Retrieve an electronic address

> Retrieve an electronic address

*Tags:* `Organisations Electronic Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Update an electronic address

> Update an electronic address

*Tags:* `Organisations Electronic Addresses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `addressId` - _required_ - The address identifier.

### Retrieve a list of licenses

*Tags:* `Organisations Licenses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Create a license

> Create a license

*Tags:* `Organisations Licenses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Delete a license

> Delete a license

*Tags:* `Organisations Licenses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Retrieve a license

> Retrieve a license

*Tags:* `Organisations Licenses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Update a license

> Update a license

*Tags:* `Organisations Licenses`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `productId` - _required_ - The product identifier.

### Retrieve a list of roles

*Tags:* `Organisations Roles`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Create a role

> Create a role

*Tags:* `Organisations Roles`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.

### Delete a role

> Delete a role

*Tags:* `Organisations Roles`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `roleId` - _required_ - The role identifier.

### Retrieve a role

> Retrieve a role

*Tags:* `Organisations Roles`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `roleId` - _required_ - The role identifier.

### Update a role

> Update a role

*Tags:* `Organisations Roles`

#### Input Parameters
* `apiKey` - _required_ - The API key.
* `partyId` - _required_ - The party identifier.
* `roleId` - _required_ - The role identifier.

## License

**flow**ground :- Telekom iPaaS / ato-gov-au-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
