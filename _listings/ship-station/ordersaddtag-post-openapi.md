---
swagger: "2.0"
x-collection-name: Ship Station
x-complete: 0
info:
  title: Ship Station Add Tag to Order
  description: |-
    Adds a tag to an order.  The body of this request should specify the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
    ``orderId`` | number, required | Identifies the order that will be tagged.
    ``tagId`` | number, required | Identifies the tag that will be applied to the order.
  version: 1.0.0
host: ssapi.shipstation.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /accounts/listtags:
    get:
      summary: List Tags
      description: Lists all tags defined for this account.
      operationId: accounts.listtags.get
      x-api-path-slug: accountslisttags-get
      responses:
        200:
          description: OK
      tags:
      - List
      - Tags
  /accounts/registeraccount:
    post:
      summary: Register Account
      description: "Creates a new ShipStation account and generates an apiKey and
        apiSecret to be used by the newly created account. PLEASE NOTE: This endpoint
        does not require API key and API Secret credentials.  The Authorization header
        can be left off. Use of this specific endpoint requires approval, and is meant
        only for direct partners of ShipStation. This is the only endpoint to require
        approval. All other endpoints listed in this document can be accessed by submitting
        proper authorization credentials in the header of the request. To become a
        direct partner of ShipStation, or to request more information on becoming
        a direct partner, we recommend reaching out to our Partners and Integrations
        team here: https://info.shipstation.com/become-a-partner-api-and-custom-store-integrations\n\nThe
        body of this request has the following attributes:\n\nName               |Data
        Type          |Description\n-------------------|-------------------|-------------------\n``firstName``
        \ | string, required | First Name\n``lastName`` | string, required | Last
        Name\n``email`` | string, required | Email address. This will also be the
        username of the account.\n``password`` | string, required | Password to set
        for account access.\n``companyName`` | string, optional | Name of Company.\n``addr1``
        | string, optional | Company Address - Street 1\n``addr2`` | string, optional
        | Company Address - Street 2\n``city`` | string, optional | Company Address
        - City\n``state`` | string, optional | Company Address - State \n``zip`` |
        string, optional | Company Address - Zip Code\n``countryCode`` |string, optional
        | Company Address - Country.  Please use a 2-character country code.\n``phone``
        | string, optional | Company Phone number."
      operationId: accounts.registeraccount.post
      x-api-path-slug: accountsregisteraccount-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Register
      - Account
  /carriers:
    get:
      summary: List Carriers
      description: Lists all shipping providers connected to this account.
      operationId: carriers.get
      x-api-path-slug: carriers-get
      responses:
        200:
          description: OK
      tags:
      - List
      - Carriers
  /carriers/addfunds:
    post:
      summary: Add Funds
      description: |-
        Adds funds to a carrier account using the payment information on file. The body of this request should specify the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
         ``carrierCode`` | string, required |  The carrier to add funds to.
         ``amount`` | number, required | The dollar amount to add to the account.  The minimum value that can be added is $10.00.  The maximum value is $10,000.00.
      operationId: carriers.addfunds.post
      x-api-path-slug: carriersaddfunds-post
      responses:
        200:
          description: OK
      tags:
      - Funds
  /carriers/getcarrier?carrierCode={carrierCode}:
    get:
      summary: Get Carrier
      description: Retrieves the shipping carrier account details for the specified
        carrierCode. Use this method to determine a carrier's account balance.
      operationId: carriers.getcarrier_carrierCode_carrierCode.get
      x-api-path-slug: carriersgetcarriercarriercodecarriercode-get
      parameters:
      - in: path
        name: carrierCode
        description: The code for the carrier account to retrieve
      responses:
        200:
          description: OK
      tags:
      - Carrier
  /carriers/listpackages?carrierCode={carrierCode}:
    get:
      summary: List Packages
      description: Retrieves a list of packages for the specified carrier
      operationId: carriers.listpackages_carrierCode_carrierCode.get
      x-api-path-slug: carrierslistpackagescarriercodecarriercode-get
      parameters:
      - in: path
        name: carrierCode
        description: The carriers code
      responses:
        200:
          description: OK
      tags:
      - List
      - Packages
  /carriers/listservices?carrierCode={carrierCode}:
    get:
      summary: List Services
      description: Retrieves the list of available shipping services provided by the
        specified carrier
      operationId: carriers.listservices_carrierCode_carrierCode.get
      x-api-path-slug: carrierslistservicescarriercodecarriercode-get
      parameters:
      - in: path
        name: carrierCode
        description: The carriers code
      responses:
        200:
          description: OK
      tags:
      - List
      - Services
  /customers/{customerId}:
    get:
      summary: Get Customer
      description: ""
      operationId: customers.customerId.get
      x-api-path-slug: customerscustomerid-get
      parameters:
      - in: path
        name: customerId
        description: The system generated identifier for the Customer
      responses:
        200:
          description: OK
      tags:
      - Customer
  ? /customers?stateCode={stateCode}&countryCode={countryCode}&tagId={tagId}&marketplaceId={marketplaceId}&sortBy={sortBy}&sortDir={sortDir}&page={page}&pageSize={pageSize}
  : get:
      summary: List Customers
      description: Obtains a list of customers that match the specified criteria.
      operationId: customers_stateCode_stateCode_countryCode_countryCode_tagId_tagId_marketplaceId_marketplaceId_sortBy
      x-api-path-slug: customersstatecodestatecodecountrycodecountrycodetagidtagidmarketplaceidmarketplaceidsortbysortbysortdirsortdirpagepagepagesizepagesize-get
      parameters:
      - in: path
        name: countryCode
        description: Returns customers that reside in the specified countryCode
      - in: path
        name: marketplaceId
        description: Returns customers that purchased items from the specified marketplaceId
      - in: path
        name: page
        description: Page number
      - in: path
        name: pageSize
        description: Requested page size
      - in: path
        name: sortBy
        description: Sorts the order of the response based off the specified value
      - in: path
        name: sortDir
        description: Sets the direction of the sort order
      - in: path
        name: stateCode
        description: Returns customers that reside in the specified stateCode
      - in: path
        name: tagId
        description: Returns customers that have been tagged with the specified tagId
      responses:
        200:
          description: OK
      tags:
      - List
      - Customers
  /fulfillments:
    get:
      summary: List Fulfillments w/o parameters
      description: ""
      operationId: fulfillments.get
      x-api-path-slug: fulfillments-get
      responses:
        200:
          description: OK
      tags:
      - List
      - Fulfillments
      - W
      - O
      - Parameters
  ? /fulfillments?fulfillmentId={fulfillmentId}&orderId={orderId}&orderNumber={orderNumber}&trackingNumber={trackingNumber}&recipientName={recipientName}&createDateStart={createDateStart}&createDateEnd={createDateEnd}&shipDateStart={shipDateStart}&shipDa
  : get:
      summary: List Fulfillments with parameters
      description: |-
        Obtains a list of fulfillments that match the specified criteria.  Please note the following:

        - Orders that have been marked as shipped either through the UI or the API will appear in the response as they are considered fulfillments.

        All of the available filters are optional.  They do not need to be included in the URL.  If you do include them, here's what the URL may look like:

        Url format with filters:

        ```
        fulfillments?fulfillmentId={fulfillmentId}
        &orderId={orderId}
        &orderNumber={orderNumber}
        &trackingNumber={trackingNumber}
        &recipientName={recipientName}
        &createDateStart={createDateStart}
        &createDateEnd={createDateEnd}
        &shipDateStart={shipDateStart}
        &shipDateEnd={shipDateEnd}
        &sortBy={sortBy}
        &sortDir={sortDir}
        &page={page}
        &pageSize={pageSize}
        ```
      operationId: fulfillments_fulfillmentId_fulfillmentId_orderId_orderId_orderNumber_orderNumber_trackingNumber_trac
      x-api-path-slug: fulfillmentsfulfillmentidfulfillmentidorderidorderidordernumberordernumbertrackingnumbertrackingnumberrecipientnamerecipientnamecreatedatestartcreatedatestartcreatedateendcreatedateendshipdatestartshipdatestartshipda-get
      parameters:
      - in: path
        name: createDateEnd
        description: Returns fulfillments created on or before the specified ``createDate``
      - in: path
        name: createDateStart
        description: Returns fulfillments created on or after the specified ``createDate``
      - in: path
        name: fulfillmentId
        description: Returns the fulfillment with the specified fulfillment ID
      - in: path
        name: orderId
        description: Returns fulfillments whose orders have the specified order ID
      - in: path
        name: orderNumber
        description: Returns fulfillments whose orders have the specified order number
      - in: path
        name: page
        description: page number
      - in: path
        name: pageSize
        description: page size
      - in: path
        name: recipientName
        description: Returns fulfillments shipped to the specified recipient name
      - in: path
        name: shipDateEnd
        description: Returns fulfillments with the ``shipDate`` on or before the specified
          date
      - in: path
        name: shipDateStart
        description: Returns fulfillments with the ``shipDate`` on or after the specified
          date
      - in: path
        name: sortBy
        description: Sort the responses by a set value
      - in: path
        name: sortDir
        description: Sets the direction of the sort order
      - in: path
        name: trackingNumber
        description: Returns fulfillments with the specified tracking number
      responses:
        200:
          description: OK
      tags:
      - List
      - Fulfillments
      - Parameters
  /orders:
    get:
      summary: List Orders w/o parameters
      description: ""
      operationId: orders.get
      x-api-path-slug: orders-get
      responses:
        200:
          description: OK
      tags:
      - List
      - Orders
      - W
      - O
      - Parameters
  /orders/addtag:
    post:
      summary: Add Tag to Order
      description: |-
        Adds a tag to an order.  The body of this request should specify the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
        ``orderId`` | number, required | Identifies the order that will be tagged.
        ``tagId`` | number, required | Identifies the tag that will be applied to the order.
      operationId: orders.addtag.post
      x-api-path-slug: ordersaddtag-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Tag
      - To
      - Order
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---