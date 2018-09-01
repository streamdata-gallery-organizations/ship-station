---
swagger: "2.0"
x-collection-name: Ship Station
x-complete: 0
info:
  title: Ship Station List Users
  description: ""
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
  /orders/unassignuser:
    post:
      summary: Unassign User from Order
      description: |-
        Unassigns a user from an order.  The body of this request should specify the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
        ``orderIds`` | number, required | Identifies set of orders that will have the user unassigned.  Please note that if ANY of the orders within the array are not found, then no orders will have their users unassigned.
      operationId: orders.unassignuser.post
      x-api-path-slug: ordersunassignuser-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Unassign
      - User
      - From
      - Order
  /orders/{orderId}:
    delete:
      summary: Delete Order
      description: Removes order from ShipStation's UI. Note this is a "soft" delete
        action so the order will still exist in the database, but will be set to ``inactive``
      operationId: orders.orderId.delete
      x-api-path-slug: ordersorderid-delete
      parameters:
      - in: path
        name: orderId
        description: The system generated identifier for the order
      responses:
        200:
          description: OK
      tags:
      - Order
    get:
      summary: Get Order
      description: Retrieves a single order from the database.
      operationId: orders.orderId.get
      x-api-path-slug: ordersorderid-get
      parameters:
      - in: path
        name: orderId
        description: The system generated identifier for the order
      responses:
        200:
          description: OK
      tags:
      - Order
  ? /orders?customerName={customerName}&itemKeyword={itemKeyword}&createDateStart={createDateStart}&createDateEnd={createDateEnd}&modifyDateStart={modifyDateStart}&modifyDateEnd={modifyDateEnd}&orderDateStart={orderDateStart}&orderDateEnd={orderDateEnd}&
  : get:
      summary: List Orders with parameters
      description: |-
        Obtains a list of orders that match the specified criteria.  All of the available filters are optional.  They do not need to be included in the URL.  If you do include them, here's what the URL may look like:

        Url format with filters:

        ```
        /orders?customerName={customerName}
        &itemKeyword={itemKeyword}
        &createDateStart={createDateStart}
        &createDateEnd={createDateEnd}
        &modifyDateStart={modifyDateStart}
        &modifyDateEnd={modifyDateEnd}
        &orderDateStart={orderDateStart}
        &orderDateEnd={orderDateEnd}
        &orderNumber={orderNumber}
        &orderStatus={orderStatus}
        &paymentDateStart={paymentDateStart}
        &paymentDateEnd={paymentDateEnd}
        &storeId={storeId}
        &sortBy={sortBy}
        &sortDir={sortDir}
        &page={page}
        &pageSize={pageSize}
        ```
      operationId: orders_customerName_customerName_itemKeyword_itemKeyword_createDateStart_createDateStart_createDateE
      x-api-path-slug: orderscustomernamecustomernameitemkeyworditemkeywordcreatedatestartcreatedatestartcreatedateendcreatedateendmodifydatestartmodifydatestartmodifydateendmodifydateendorderdatestartorderdatestartorderdateendorderdateend-get
      parameters:
      - in: path
        name: createDateEnd
        description: Returns orders that were created in ShipStation before the specified
          date
      - in: path
        name: createDateStart
        description: Returns orders that were created in ShipStation after the specified
          date
      - in: path
        name: customerName
        description: Returns orders that match the specified name
      - in: path
        name: itemKeyword
        description: Returns orders that contain items that match the specified keyword
      - in: path
        name: modifyDateEnd
        description: Returns orders that were modified before the specified date
      - in: path
        name: modifyDateStart
        description: Returns orders that were modified after the specified date
      - in: path
        name: orderDateEnd
        description: Returns orders less than or equal to the specified date
      - in: path
        name: orderDateStart
        description: Returns orders greater than the specified date
      - in: path
        name: orderNumber
        description: Filter by order number, performs a starts with search
      - in: path
        name: orderStatus
        description: Filter by order status
      - in: path
        name: page
        description: Page number
      - in: path
        name: pageSize
        description: Requested page size
      - in: path
        name: paymentDateEnd
        description: Returns orders that were paid before the specified date
      - in: path
        name: paymentDateStart
        description: Returns orders that were paid after the specified date
      - in: path
        name: sortBy
        description: Sort the responses by a set value
      - in: path
        name: sortDir
        description: Sets the direction of the sort order
      - in: path
        name: storeId
        description: Filters orders to a single store
      responses:
        200:
          description: OK
      tags:
      - List
      - Orders
      - Parameters
  /products:
    get:
      summary: List Products w/o parameters
      description: ""
      operationId: products.get
      x-api-path-slug: products-get
      responses:
        200:
          description: OK
      tags:
      - List
      - Products
      - W
      - O
      - Parameters
  /products/{productId}:
    get:
      summary: Get Product
      description: ""
      operationId: products.productId.get
      x-api-path-slug: productsproductid-get
      parameters:
      - in: path
        name: productId
        description: The system generated identifier for the Product
      responses:
        200:
          description: OK
      tags:
      - Product
    put:
      summary: Update Product
      description: Updates an existing product. This call does not currently support
        partial updates. The entire resource must be provided in the body of the request.
      operationId: products.productId.put
      x-api-path-slug: productsproductid-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: productId
        description: The system generated identifier for the Product
      responses:
        200:
          description: OK
      tags:
      - Product
  ? /products?sku={sku}&name={name}&productCategoryId={productCategoryId}&productTypeId={productTypeId}&tagId={tagId}&startDate={startDate}&endDate={endDate}&showInactive={showInactive}&sortBy={sortBy}&sortDir={sortDir}&page={page}&pageSize={pageSize}
  : get:
      summary: List Products with parameters
      description: |-
        Obtains a list of products that match the specified criteria.  All of the available filters are optional.  They do not need to be included in the URL.  If you do include them, here's what the URL may look like:

        Url format with filters:

        ```
        /products?sku={sku}
        &name={name}
        &productCategoryId={productCategoryId}
        &productTypeId={productTypeId}
        &tagId={tagId}
        &startDate={startDate}
        &endDate={endDate}
        &showInactive={showInactive}
        &sortBy={sortBy}
        &sortDir={sortDir}
        &page={page}
        &pageSize={pageSize}
        ```
      operationId: products_sku_sku_name_name_productCategoryId_productCategoryId_productTypeId_productTypeId_tagId_tag
      x-api-path-slug: productsskuskunamenameproductcategoryidproductcategoryidproducttypeidproducttypeidtagidtagidstartdatestartdateenddateenddateshowinactiveshowinactivesortbysortbysortdirsortdirpagepagepagesizepagesize-get
      parameters:
      - in: path
        name: endDate
        description: Returns products that were created before the specified date
      - in: path
        name: name
        description: Returns products that match the specified product name
      - in: path
        name: page
        description: Page number
      - in: path
        name: pageSize
        description: Requested page size
      - in: path
        name: productCategoryId
        description: Returns products that match the specified productCategoryId
      - in: path
        name: productTypeId
        description: Returns products that match the specified productTypeId
      - in: path
        name: showInactive
        description: Specifies whether the list should include inactive products
      - in: path
        name: sku
        description: Returns products that match the specified SKU
      - in: path
        name: sortBy
        description: Sorts the order of the response based off the specified value
      - in: path
        name: sortDir
        description: Sets the direction of the sort order
      - in: path
        name: startDate
        description: Returns products that were created after the specified date
      - in: path
        name: tagId
        description: Returns products that match the specified tagId
      responses:
        200:
          description: OK
      tags:
      - List
      - Products
      - Parameters
  /shipments:
    get:
      summary: List Shipments w/o parameters
      description: ""
      operationId: shipments.get
      x-api-path-slug: shipments-get
      responses:
        200:
          description: OK
      tags:
      - List
      - Shipments
      - W
      - O
      - Parameters
  /shipments/createlabel:
    post:
      summary: Create Shipment Label
      description: "Creates a shipping label.  The ``labelData`` field returned in
        the response is a base64 encoded PDF value. Simply decode and save the output
        as a PDF file to retrieve a printable label.  The body of this request has
        the following attributes:\n\nName               |Data Type          |Description\n-------------------|-------------------|-------------------\n
        ``carrierCode`` | string, required | Identifies the carrier to be used for
        this label.\n ``serviceCode`` | string, required | Identifies the shipping
        service to be used for this label.\n ``packageCode`` | string, required |
        Identifies the packing type that should be used for this label.\n ``confirmation``
        | string, optional | Identifies the delivery confirmation type to be used
        for this label.\n ``shipDate`` | string, required | The date the shipment
        will be shipped.\n ``weight`` | Weight, required | Shipment's weight.  Use
        the [**Weight**](https://www.shipstation.com/developer-api/#/reference/model-weight)
        model.\n ``dimensions`` | Dimensions, optional | Shipment's dimensions.  Use
        the [**Dimensions**](https://www.shipstation.com/developer-api/#/reference/model-dimensions)
        model.\n ``shipFrom`` | Address, required | Address indicating shipment's
        origin.  Use the [**Address**](https://www.shipstation.com/developer-api/#/reference/model-address)
        model.\n ``shipTo`` | Address, required | Address indicating shipment's destination.
        \ Use the [**Address**](https://www.shipstation.com/developer-api/#/reference/model-address)
        model.\n ``insuranceOptions`` | InsuranceOptions, optional | The shipping
        insurance information associated with this order.  \n ``internationalOptions``
        | InternationalOptions, optional | Customs information that can be used to
        generate customs documents for international orders.  Use the [**InternationalOptions**](https://www.shipstation.com/developer-api/#/reference/model-internationaloptions)
        model.\n ``advancedOptions`` | AdvancedOptions, optional | Various advanced
        options that may be available depending on the shipping carrier that is used
        to ship the order.  Use the [**AdvancedOptions**](https://www.shipstation.com/developer-api/#/reference/model-advancedoptions)
        model. \n ``testLabel`` | boolean, optional | Specifies whether a test label
        should be created. Default value: false."
      operationId: shipments.createlabel.post
      x-api-path-slug: shipmentscreatelabel-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Shipment
      - Label
  /shipments/getrates:
    post:
      summary: Get Rates
      description: "Retrieves shipping rates for the specified shipping details.  The
        body of this request should specify the following attributes:\n\nName               |Data
        Type          |Description\n-------------------|-------------------|-------------------\n
        ``carrierCode`` | string, required | Returns rates for the specified carrier.\n
        ``serviceCode`` | string, optional | Returns rates for the specified shipping
        service.\n ``packageCode`` | string, optional | Returns rates for the specified
        package type.\n ``fromPostalCode`` | string, required | Originating postal
        code.\n ``toState`` | string, optional | Destination State/Province. Please
        use two-character state/province abbreviation. Note this field is required
        for the following carriers: UPS\n ``toCountry`` | string, required | Destination
        Country.  Please use the two-character ISO country code.\n ``toPostalCode``
        | string, required | Destination Postal Code.\n ``toCity`` | string, optional
        | Destination City.\n ``weight`` | Weight, required | Shipment's weight.  Use
        ``Weight`` object.\n ``dimensions`` | Dimensions, optional | Shipment's dimensions.
        \ Use ``Dimensions`` object. \n ``confirmation`` | string, optional | Returns
        rates that account for the specified delivery confirmation type.\n ``residential``
        | boolean, optional | Returns rates that account for the specified delivery
        confirmation type. Default value: false"
      operationId: shipments.getrates.post
      x-api-path-slug: shipmentsgetrates-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Rates
  /shipments/voidlabel:
    post:
      summary: Void Label
      description: |-
        Voids the specified label by shipmentId.  The body of this request should specify the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
         ``shipmentId`` | number, required | ID of the shipment to void.
      operationId: shipments.voidlabel.post
      x-api-path-slug: shipmentsvoidlabel-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Void
      - Label
  ? /shipments?recipientName={recipientName}&recipientCountryCode={recipientCountryCode}&orderNumber={orderNumber}&orderId={orderId}&carrierCode={carrierCode}&serviceCode={serviceCode}&trackingNumber={trackingNumber}&createDateStart={createDateStart}&cre
  : get:
      summary: List Shipments with parameters
      description: |-
        Obtains a list of shipments that match the specified criteria.  Please note the following:

        - Only valid shipments with labels generated in ShipStation will be returned in the response. Orders that have been marked as shipped either through the UI or the API will not appear as they are considered external shipments.

        - To include every shipment's associated shipmentItems in the response, be sure to set the `includeShipmentItems` parameter to `true`.

        All of the available filters are optional.  They do not need to be included in the URL.  If you do include them, here's what the URL may look like:

        Url format with filters:

        ```
        shipments?recipientName={recipientName}
        &recipientCountryCode={recipientCountryCode}
        &orderNumber={orderNumber}
        &orderId={orderId}
        &carrierCode={carrierCode}
        &serviceCode={serviceCode}
        &trackingNumber={trackingNumber}
        &createDateStart={createDateStart}
        &createDateEnd={createDateEnd}
        &shipDateStart={shipDateStart}
        &shipDateEnd={shipDateEnd}
        &voidDateStart={voidDateStart}
        &voidDateEnd={voidDateEnd}
        &includeShipmentItems={includeShipmentItems}
        &sortBy={sortBy}
        &sortDir={sortDir}
        &page={page}
        &pageSize={pageSize}
        ```
      operationId: shipments_recipientName_recipientName_recipientCountryCode_recipientCountryCode_orderNumber_orderNum
      x-api-path-slug: shipmentsrecipientnamerecipientnamerecipientcountrycoderecipientcountrycodeordernumberordernumberorderidorderidcarriercodecarriercodeservicecodeservicecodetrackingnumbertrackingnumbercreatedatestartcreatedatestartcre-get
      parameters:
      - in: path
        name: carrierCode
        description: Returns shipments shipped with the specified carrier
      - in: path
        name: createDateEnd
        description: Returns shipments created on or before the specified ``createDate``
      - in: path
        name: createDateStart
        description: Returns shipments created on or after the specified ``createDate``
      - in: path
        name: includeShipmentItems
        description: 'Specifies whether to include shipment items with results Default
          value: false'
      - in: path
        name: orderId
        description: Returns shipments whose orders have the specified order ID
      - in: path
        name: orderNumber
        description: Returns shipments whose orders have the specified order number
      - in: path
        name: page
        description: page number
      - in: path
        name: pageSize
        description: page size
      - in: path
        name: recipientCountryCode
        description: Returns shipments shipped to the specified country code
      - in: path
        name: recipientName
        description: Returns shipments shipped to the specified recipient name
      - in: path
        name: serviceCode
        description: Returns shipments shipped with the specified shipping service
      - in: path
        name: shipDateEnd
        description: Returns shipments with the ``shipDate`` on or before the specified
          date
      - in: path
        name: shipDateStart
        description: Returns shipments with the ``shipDate`` on or after the specified
          date
      - in: path
        name: sortBy
        description: Sort the responses by a set value
      - in: path
        name: sortDir
        description: Sets the direction of the sort order
      - in: path
        name: trackingNumber
        description: Returns shipments with the specified tracking number
      - in: path
        name: voidDateEnd
        description: Returns shipments voided on or before the specified date
      - in: path
        name: voidDateStart
        description: Returns shipments voided on or after the specified date
      responses:
        200:
          description: OK
      tags:
      - List
      - Shipments
      - Parameters
  /stores/deactivate:
    post:
      summary: Deactivate Store
      description: |-
        Deactivates the specified store.

        The body of this request has the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
        ``storeId``  | number, required | ID of the store to deactivate.
      operationId: stores.deactivate.post
      x-api-path-slug: storesdeactivate-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Deactivate
      - Store
  /stores/getrefreshstatus?storeId={storeId}:
    get:
      summary: Get Store Refresh Status
      description: Retrieves the refresh status of a given store.
      operationId: stores.getrefreshstatus_storeId_storeId.get
      x-api-path-slug: storesgetrefreshstatusstoreidstoreid-get
      parameters:
      - in: path
        name: storeId
        description: Specifies the store whose status will be retrieved
      responses:
        200:
          description: OK
      tags:
      - Store
      - Refresh
      - Status
  /stores/marketplaces:
    get:
      summary: List Marketplaces
      description: Lists the marketplaces that can be integrated with ShipStation.
      operationId: stores.marketplaces.get
      x-api-path-slug: storesmarketplaces-get
      responses:
        200:
          description: OK
      tags:
      - List
      - Marketplaces
  /stores/reactivate:
    post:
      summary: Reactivate Store
      description: |-
        Reactivates the specified store. Note: stores are active by default

        The body of this request has the following attributes:

        Name               |Data Type          |Description
        -------------------|-------------------|-------------------
        ``storeId``  | number, required | ID of the store to reactivate.
      operationId: stores.reactivate.post
      x-api-path-slug: storesreactivate-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Reactivate
      - Store
  /stores/refreshstore?storeId={storeId}&refreshDate={refreshDate}:
    post:
      summary: Refresh Store
      description: Initiates a store refresh.
      operationId: stores.refreshstore_storeId_storeId_refreshDate_refreshDate.post
      x-api-path-slug: storesrefreshstorestoreidstoreidrefreshdaterefreshdate-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: refreshDate
        description: Specifies the starting date for new order imports
      - in: path
        name: storeId
        description: Specifies the store which will get refreshed
      responses:
        200:
          description: OK
      tags:
      - Refresh
      - Store
  /stores/{storeId}:
    get:
      summary: Get Store
      description: ""
      operationId: stores.storeId.get
      x-api-path-slug: storesstoreid-get
      parameters:
      - in: path
        name: storeId
        description: A unique ID generated by ShipStation and assigned to each store
      responses:
        200:
          description: OK
      tags:
      - Store
    put:
      summary: Update Store
      description: Updates an existing store. This call does not currently support
        partial updates. The entire resource must be provided in the body of the request.
      operationId: stores.storeId.put
      x-api-path-slug: storesstoreid-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: storeId
        description: A unique ID generated by ShipStation and assigned to each store
      responses:
        200:
          description: OK
      tags:
      - Store
  /stores?showInactive={showInactive}&marketplaceId={marketplaceId}:
    get:
      summary: List Stores
      description: Retrieve the list of installed stores on the account.
      operationId: stores_showInactive_showInactive_marketplaceId_marketplaceId.get
      x-api-path-slug: storesshowinactiveshowinactivemarketplaceidmarketplaceid-get
      parameters:
      - in: path
        name: marketplaceId
        description: Returns stores of this marketplace type
      - in: path
        name: showInactive
        description: Determines whether inactive stores will be returned in the list
          of stores
      responses:
        200:
          description: OK
      tags:
      - List
      - Stores
  /users?showInactive={showInactive}:
    get:
      summary: List Users
      description: ""
      operationId: users_showInactive_showInactive.get
      x-api-path-slug: usersshowinactiveshowinactive-get
      parameters:
      - in: path
        name: showInactive
        description: Determines whether inactive users will be returned in the response
      responses:
        200:
          description: OK
      tags:
      - List
      - Users
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