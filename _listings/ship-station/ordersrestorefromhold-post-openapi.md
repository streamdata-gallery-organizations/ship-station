---
swagger: "2.0"
x-collection-name: Ship Station
x-complete: 0
info:
  title: Ship Station Restore Order from On Hold
  description: |-
    This method will change the status of the given order from On Hold to Awaiting Shipment. This endpoint is used when a holdUntil Date is attached to an order.

    The body of this request should specify the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
    ``orderId`` | number, required | Identifies the order that will be restored to ``awaiting_shipment`` from ``on_hold``.
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
  /orders/assignuser:
    post:
      summary: Assign User to Order
      description: |-
        Assigns a user to an order.  The body of this request should specify the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
        ``orderIds`` | number, required | Identifies set of orders that will be assigned the user.  Please note that if ANY of the orders within the array are not found, no orders will have a user assigned to them.
        ``userId`` | number, required | Identifies the user that will be applied to the orders.  It should contain a GUID of the user to be assigned to the array of orders.
      operationId: orders.assignuser.post
      x-api-path-slug: ordersassignuser-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Assign
      - User
      - To
      - Order
  /orders/createlabelfororder:
    post:
      summary: Create Label for Order
      description: |-
        Creates a shipping label for a given order.  The ``labelData`` field returned in the response is a base64 encoded PDF value. Simply decode and save the output as a PDF file to retrieve a printable label.  The body of this request should specify the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
        ``orderId`` | number, required | Identifies the order that will be shipped.
        ``carrierCode`` | string, required | The code for the carrier that is to be used for the label.
        ``serviceCode`` | string, required | The code for the shipping service that is to be used for the label.
        ``confirmation`` | string, required | The type of delivery confirmation that is to be used once the shipment is created.  Possible values: ``none``, ``delivery``, ``signature``, ``adult_signature``, and ``direct_signature``.  ``direct_signature`` is available for FedEx only.
        ``shipDate`` | string, required | The date the order should be shipped.
        ``weight`` | Weight, optional | Weight of the order.  Use the [**Weight**](http://www.shipstation.com/developer-api/#/reference/model-weight) model.
        ``dimensions`` | Dimensions, optional | Dimensions of the order.  Use [**Dimensions**](http://www.shipstation.com/developer-api/#/reference/model-dimensions) model.
        ``insuranceOptions`` | InsuranceOptions, optional | The shipping insurance information associated with this label.  Use the [**InsuranceOptions**](http://www.shipstation.com/developer-api/#/reference/model-insuranceoptions) model.
        ``internationalOptions`` | InternationalOptions, optional | Customs information that can be used to generate customs documents for international orders.  Use the [**InternationalOptions**](http://www.shipstation.com/developer-api/#/reference/model-internationaloptions) model.
        ``advancedOptions`` | AdvancedOptions, optional | Various advanced options that may be available depending on the shipping carrier that is used to ship the order. Use the Customs information that can be used to generate customs documents for international orders.  Use the [**AdvancedOptions**](http://www.shipstation.com/developer-api/#/reference/model-advancedoptions) model.
        ``testLabel`` | boolean, required | Specifies whether a test label should be created.
      operationId: orders.createlabelfororder.post
      x-api-path-slug: orderscreatelabelfororder-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - LabelOrder
  /orders/createorder:
    post:
      summary: Create/Update Order
      description: "If the ``orderKey`` is specified, the method becomes idempotent
        and the existing order with that key will be updated. Note: Only orders in
        an open status in ShipStation (``awaiting_payment``,``awaiting_shipment``,
        and ``on_hold``) can be updated through this method. ``cancelled`` and ``shipped``
        are locked from modification through the API.  The body of this request should
        specify an [**Order**](https://www.shipstation.com/developer-api/#/reference/model-order)
        object:\n\nName               |Data Type          |Description\n-------------------|-------------------|-------------------\n``orderNumber``
        | string, required | A user-defined order number used to identify an order.\n``orderKey``
        | string, optional | A user-provided key that should be unique to each order.
        \ If an orderKey is not provided, ShipStation will create a new order and
        generate a unique orderKey for that order.  If the orderKey *is* provided,
        the **createorder** method will either: create a new order if the provided
        orderKey is not found, or, update the existing order if the orderKey is found.\n``orderDate``
        | string, required | The date the order was placed.\n``paymentDate`` | string,
        optional | The date the order was paid for.\n``shipByDate`` | string, optional
        | The date the order is to be shipped before or on. This field is a suggested
        value generated by the order source/platform/cart and passed to ShipStation.\n``orderStatus``
        | string, required | The order's status. Possible values: ``awaiting_payment``,
        ``awaiting_shipment``, ``shipped``, ``on_hold``, ``cancelled``\n``customerUsername``
        | string, optional | The customer's username.\n``customerEmail`` | string,
        optional | The customer's email address.\n``billTo`` | Address, required |
        The recipients billing address. Use the [**Address**](https://www.shipstation.com/developer-api/#/reference/model-address)
        model.\n``shipTo`` | Address, required | The recipient's shipping address.
        Use the [**Address**](http://www.shipstation.com/developer-api/#/reference/model-address)
        model.\n``items`` | OrderItem, optional | An array of item objects.  Use an
        array of [**OrderItem**](http://www.shipstation.com/developer-api/#/reference/model-orderitem)
        models.\n``amountPaid`` | number, optional | The total amount paid for the
        Order.\n``taxAmount`` | number, optional | The total tax amount for the Order.\n``shippingAmount``
        | number, optional | Shipping amount paid by the customer, if any.\n``customerNotes``
        | string, optional | Notes left by the customer when placing the order.\n``internalNotes``
        | string, optional | Private notes that are only visible to the seller.\n``gift``
        | boolean, optional | Specifies whether or not this Order is a gift\n``giftMessage``
        | string, optional | Gift message left by the customer when placing the order.\n``paymentMethod``
        | string, optional | Identifies the shipping service selected by the customer
        when placing this order.\n``requestedShippingService`` | string, optional
        |Identifies the shipping service selected by the customer when placing this
        order. This value is given to ShipStation by the marketplace/cart and helps
        identify what shipping service the customer selected upon checkout.\n``carrierCode``
        | string, optional | The code for the carrier that is to be used(or was used)
        when this order is shipped(was shipped).\n``serviceCode`` | string, optional
        | The code for the shipping service that is to be used(or was used) when this
        order is shipped(was shipped).\n``packageCode`` | string, optional | The code
        for the package type that is to be used(or was used) when this order is shipped(was
        shipped).\n``confirmation`` | string, optional | The type of delivery confirmation
        that is to be used(or was used) when this order is shipped(was shipped). Possible
        values: ``none``, ``delivery``, ``signature``, ``adult_signature``, and ``direct_signature``.
        \ ``direct_signature`` is available for FedEx only.  \n``shipDate`` | string,
        optional | The date the order was shipped.\n``weight`` | Weight, optional
        | Weight of the order.  Use the [**Weight**](http://www.shipstation.com/developer-api/#/reference/model-weight)
        model.\n``dimensions`` | Dimensions, optional | Dimensions of the order.  Use
        the [**Dimensions**](http://www.shipstation.com/developer-api/#/reference/model-dimensions)
        model.\n``insuranceOptions`` | InsuranceOptions, optional | The shipping insurance
        information associated with this order.  Use the [**InsuranceOptions**](http://www.shipstation.com/developer-api/#/reference/model-insuranceoptions)
        model.\n``internationalOptions`` | InternationalOptions, optional | Customs
        information that can be used to generate customs documents for international
        orders.  Use the [**InternationalOptions**](http://www.shipstation.com/developer-api/#/reference/model-internationaloptions)
        model.\n``advancedOptions`` | AdvancedOptions, optional | Various advanced
        options that may be available depending on the shipping carrier that is used
        to ship the order. Use the [**AdvancedOptions**](http://www.shipstation.com/developer-api/#/reference/model-advancedoptions)
        model."
      operationId: orders.createorder.post
      x-api-path-slug: orderscreateorder-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Order
  /orders/createorders:
    post:
      summary: Create/Update Multiple Orders
      description: |-
        This endpoint can be used to create or update multiple orders in one request. If the ``orderKey`` is specified in an order, the existing order with that key will be updated. Note: Only orders in an open status in ShipStation (``awaiting_payment``,``awaiting_shipment``, and ``on_hold``) can be updated through this method. ``cancelled`` and ``shipped`` are locked from modification through the API.

        Data Type          |Description
        -------------------|-------------------
        Order, required | An array of [**Order**](http://www.shipstation.com/developer-api/#/reference/model-order) objects (maximum of 100 per request)
      operationId: orders.createorders.post
      x-api-path-slug: orderscreateorders-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Multiple
      - Orders
  /orders/holduntil:
    post:
      summary: Hold Order Until
      description: |-
        This method will change the status of the given order to On Hold until the date specified, when the status will automatically change to Awaiting Shipment.

        The body of this request should specify the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
        ``orderId`` | number, required | Identifies the order that will be held.
        ``holdUntilDate`` | string, required | Date when order is moved from ``on_hold`` status to ``awaiting_shipment``.
      operationId: orders.holduntil.post
      x-api-path-slug: ordersholduntil-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Hold
      - Order
      - Until
  /orders/listbytag?orderStatus={orderStatus}&tagId={tagId}&page={page}&pageSize={pageSize}:
    get:
      summary: List Orders by Tag
      description: |-
        Lists all orders that match the specified status and tag ID.

        Url format with filters:

        ```
        /listbytag?orderStatus={orderStatus}
        &tagId={tagId}
        &page={page}
        &pageSize={pageSize}
        ```
      operationId: orders.listbytag_orderStatus_orderStatus_tagId_tagId_page_page_pageSize_pageSize.get
      x-api-path-slug: orderslistbytagorderstatusorderstatustagidtagidpagepagepagesizepagesize-get
      parameters:
      - in: path
        name: orderStatus
        description: The orders status
      - in: path
        name: page
        description: Page number
      - in: path
        name: pageSize
        description: Requested page size
      - in: path
        name: tagId
        description: ID of the tag
      responses:
        200:
          description: OK
      tags:
      - List
      - Orders
      - By
      - Tag
  /orders/markasshipped:
    post:
      summary: Mark an Order as Shipped
      description: |-
        Marks an order as shipped without creating a label in ShipStation. The body of this request has the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
         ``orderId`` | number, required | Identifies the order that will be marked as shipped.
         ``carrierCode`` | string, required | Code of the carrier that is marked as having shipped the order.
         ``shipDate`` | string, optional | Date order was shipped.
         ``trackingNumber`` | string, optional | Tracking number of shipment.
         ``notifyCustomer``  | boolean, optional | Specifies whether the customer should be notified of the shipment. Default value: false
         ``notifySalesChannel`` | boolean, optional | Specifies whether the sales channel should be notified of the shipment. Default value: false
      operationId: orders.markasshipped.post
      x-api-path-slug: ordersmarkasshipped-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Mark
      - Order
      - As
      - Shipped
  /orders/removetag:
    post:
      summary: Remove Tag from Order
      description: |-
        Removes a tag from the specified order.  The body of this request has the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
        ``orderId`` | number, required | Identifies the order whose tag will be removed.
        ``tagId`` | number, required | Identifies the tag to remove.
      operationId: orders.removetag.post
      x-api-path-slug: ordersremovetag-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Remove
      - Tag
      - From
      - Order
  /orders/restorefromhold:
    post:
      summary: Restore Order from On Hold
      description: |-
        This method will change the status of the given order from On Hold to Awaiting Shipment. This endpoint is used when a holdUntil Date is attached to an order.

        The body of this request should specify the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
        ``orderId`` | number, required | Identifies the order that will be restored to ``awaiting_shipment`` from ``on_hold``.
      operationId: orders.restorefromhold.post
      x-api-path-slug: ordersrestorefromhold-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Restore
      - Order
      - From
      - "On"
      - Hold
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