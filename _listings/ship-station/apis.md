---
name: Ship Station
x-slug: ship-station
description: ShipStation is a web-based shipping solution that streamlines the order
  fulfillment process for your online business. ShipStation consolidates orders from
  over 70 ecommerce channels, creates shipping labels, packing slips, and pick lists
  in batch, communicates tracking information to your customers, provides endless
  automation, filters, and views, wireless printing, a mobile app, and a lot more.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
x-kinRank: "7"
x-alexaRank: "0"
tags: Ship Station
created: "2018-08-31"
modified: "2018-08-31"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/apis.md
specificationVersion: "0.14"
apis:
- name: Ship Station Developer Portal - List Tags
  x-api-slug: accountslisttags-get
  description: Lists all tags defined for this account.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/accountslisttags-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/accountslisttags-get-openapi.md
- name: Ship Station Developer Portal - Register Account
  x-api-slug: accountsregisteraccount-post
  description: "Creates a new ShipStation account and generates an apiKey and apiSecret
    to be used by the newly created account. PLEASE NOTE: This endpoint does not require
    API key and API Secret credentials.  The Authorization header can be left off.
    Use of this specific endpoint requires approval, and is meant only for direct
    partners of ShipStation. This is the only endpoint to require approval. All other
    endpoints listed in this document can be accessed by submitting proper authorization
    credentials in the header of the request. To become a direct partner of ShipStation,
    or to request more information on becoming a direct partner, we recommend reaching
    out to our Partners and Integrations team here: https://info.shipstation.com/become-a-partner-api-and-custom-store-integrations\n\nThe
    body of this request has the following attributes:\n\nName               |Data
    Type          |Description\n-------------------|-------------------|-------------------\n``firstName``
    \ | string, required | First Name\n``lastName`` | string, required | Last Name\n``email``
    | string, required | Email address. This will also be the username of the account.\n``password``
    | string, required | Password to set for account access.\n``companyName`` | string,
    optional | Name of Company.\n``addr1`` | string, optional | Company Address -
    Street 1\n``addr2`` | string, optional | Company Address - Street 2\n``city``
    | string, optional | Company Address - City\n``state`` | string, optional | Company
    Address - State \n``zip`` | string, optional | Company Address - Zip Code\n``countryCode``
    |string, optional | Company Address - Country.  Please use a 2-character country
    code.\n``phone`` | string, optional | Company Phone number."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/accountsregisteraccount-post-openapi.md
- name: Ship Station Developer Portal - List Carriers
  x-api-slug: carriers-get
  description: Lists all shipping providers connected to this account.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/carriers-get-openapi.md
- name: Ship Station Developer Portal - Add Funds
  x-api-slug: carriersaddfunds-post
  description: |-
    Adds funds to a carrier account using the payment information on file. The body of this request should specify the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
     ``carrierCode`` | string, required |  The carrier to add funds to.
     ``amount`` | number, required | The dollar amount to add to the account.  The minimum value that can be added is $10.00.  The maximum value is $10,000.00.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/carriersaddfunds-post-openapi.md
- name: Ship Station Developer Portal - Get Carrier
  x-api-slug: carriersgetcarriercarriercodecarriercode-get
  description: Retrieves the shipping carrier account details for the specified carrierCode.
    Use this method to determine a carrier's account balance.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/carriersgetcarriercarriercodecarriercode-get-openapi.md
- name: Ship Station Developer Portal - List Packages
  x-api-slug: carrierslistpackagescarriercodecarriercode-get
  description: Retrieves a list of packages for the specified carrier
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/carrierslistpackagescarriercodecarriercode-get-openapi.md
- name: Ship Station Developer Portal - List Services
  x-api-slug: carrierslistservicescarriercodecarriercode-get
  description: Retrieves the list of available shipping services provided by the specified
    carrier
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/carrierslistservicescarriercodecarriercode-get-openapi.md
- name: Ship Station Developer Portal - Get Customer
  x-api-slug: customerscustomerid-get
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/customerscustomerid-get-openapi.md
- name: Ship Station Developer Portal - List Customers
  x-api-slug: customersstatecodestatecodecountrycodecountrycodetagidtagidmarketplaceidmarketplaceidsortbysortbysortdirsortdirpagepagepagesizepagesize-get
  description: Obtains a list of customers that match the specified criteria.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/customersstatecodestatecodecountrycodecountrycodetagidtagidmarketplaceidmarketplaceidsortbysortbysortdirsortdirpagepagepagesizepagesize-get-openapi.md
- name: Ship Station Developer Portal - List Fulfillments w/o parameters
  x-api-slug: fulfillments-get
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/fulfillments-get-openapi.md
- name: Ship Station Developer Portal - List Fulfillments with parameters
  x-api-slug: fulfillmentsfulfillmentidfulfillmentidorderidorderidordernumberordernumbertrackingnumbertrackingnumberrecipientnamerecipientnamecreatedatestartcreatedatestartcreatedateendcreatedateendshipdatestartshipdatestartshipda-get
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/fulfillmentsfulfillmentidfulfillmentidorderidorderidordernumberordernumbertrackingnumbertrackingnumberrecipientnamerecipientnamecreatedatestartcreatedatestartcreatedateendcreatedateendshipdatestartshipdatestartshipda-get-openapi.md
- name: Ship Station Developer Portal - List Orders w/o parameters
  x-api-slug: orders-get
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/orders-get-openapi.md
- name: Ship Station Developer Portal - Add Tag to Order
  x-api-slug: ordersaddtag-post
  description: |-
    Adds a tag to an order.  The body of this request should specify the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
    ``orderId`` | number, required | Identifies the order that will be tagged.
    ``tagId`` | number, required | Identifies the tag that will be applied to the order.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/ordersaddtag-post-openapi.md
- name: Ship Station Developer Portal - Assign User to Order
  x-api-slug: ordersassignuser-post
  description: |-
    Assigns a user to an order.  The body of this request should specify the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
    ``orderIds`` | number, required | Identifies set of orders that will be assigned the user.  Please note that if ANY of the orders within the array are not found, no orders will have a user assigned to them.
    ``userId`` | number, required | Identifies the user that will be applied to the orders.  It should contain a GUID of the user to be assigned to the array of orders.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/ordersassignuser-post-openapi.md
- name: Ship Station Developer Portal - Create Label for Order
  x-api-slug: orderscreatelabelfororder-post
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/orderscreatelabelfororder-post-openapi.md
- name: Ship Station Developer Portal - Create/Update Order
  x-api-slug: orderscreateorder-post
  description: "If the ``orderKey`` is specified, the method becomes idempotent and
    the existing order with that key will be updated. Note: Only orders in an open
    status in ShipStation (``awaiting_payment``,``awaiting_shipment``, and ``on_hold``)
    can be updated through this method. ``cancelled`` and ``shipped`` are locked from
    modification through the API.  The body of this request should specify an [**Order**](https://www.shipstation.com/developer-api/#/reference/model-order)
    object:\n\nName               |Data Type          |Description\n-------------------|-------------------|-------------------\n``orderNumber``
    | string, required | A user-defined order number used to identify an order.\n``orderKey``
    | string, optional | A user-provided key that should be unique to each order.
    \ If an orderKey is not provided, ShipStation will create a new order and generate
    a unique orderKey for that order.  If the orderKey *is* provided, the **createorder**
    method will either: create a new order if the provided orderKey is not found,
    or, update the existing order if the orderKey is found.\n``orderDate`` | string,
    required | The date the order was placed.\n``paymentDate`` | string, optional
    | The date the order was paid for.\n``shipByDate`` | string, optional | The date
    the order is to be shipped before or on. This field is a suggested value generated
    by the order source/platform/cart and passed to ShipStation.\n``orderStatus``
    | string, required | The order's status. Possible values: ``awaiting_payment``,
    ``awaiting_shipment``, ``shipped``, ``on_hold``, ``cancelled``\n``customerUsername``
    | string, optional | The customer's username.\n``customerEmail`` | string, optional
    | The customer's email address.\n``billTo`` | Address, required | The recipients
    billing address. Use the [**Address**](https://www.shipstation.com/developer-api/#/reference/model-address)
    model.\n``shipTo`` | Address, required | The recipient's shipping address. Use
    the [**Address**](http://www.shipstation.com/developer-api/#/reference/model-address)
    model.\n``items`` | OrderItem, optional | An array of item objects.  Use an array
    of [**OrderItem**](http://www.shipstation.com/developer-api/#/reference/model-orderitem)
    models.\n``amountPaid`` | number, optional | The total amount paid for the Order.\n``taxAmount``
    | number, optional | The total tax amount for the Order.\n``shippingAmount`` |
    number, optional | Shipping amount paid by the customer, if any.\n``customerNotes``
    | string, optional | Notes left by the customer when placing the order.\n``internalNotes``
    | string, optional | Private notes that are only visible to the seller.\n``gift``
    | boolean, optional | Specifies whether or not this Order is a gift\n``giftMessage``
    | string, optional | Gift message left by the customer when placing the order.\n``paymentMethod``
    | string, optional | Identifies the shipping service selected by the customer
    when placing this order.\n``requestedShippingService`` | string, optional |Identifies
    the shipping service selected by the customer when placing this order. This value
    is given to ShipStation by the marketplace/cart and helps identify what shipping
    service the customer selected upon checkout.\n``carrierCode`` | string, optional
    | The code for the carrier that is to be used(or was used) when this order is
    shipped(was shipped).\n``serviceCode`` | string, optional | The code for the shipping
    service that is to be used(or was used) when this order is shipped(was shipped).\n``packageCode``
    | string, optional | The code for the package type that is to be used(or was used)
    when this order is shipped(was shipped).\n``confirmation`` | string, optional
    | The type of delivery confirmation that is to be used(or was used) when this
    order is shipped(was shipped). Possible values: ``none``, ``delivery``, ``signature``,
    ``adult_signature``, and ``direct_signature``.  ``direct_signature`` is available
    for FedEx only.  \n``shipDate`` | string, optional | The date the order was shipped.\n``weight``
    | Weight, optional | Weight of the order.  Use the [**Weight**](http://www.shipstation.com/developer-api/#/reference/model-weight)
    model.\n``dimensions`` | Dimensions, optional | Dimensions of the order.  Use
    the [**Dimensions**](http://www.shipstation.com/developer-api/#/reference/model-dimensions)
    model.\n``insuranceOptions`` | InsuranceOptions, optional | The shipping insurance
    information associated with this order.  Use the [**InsuranceOptions**](http://www.shipstation.com/developer-api/#/reference/model-insuranceoptions)
    model.\n``internationalOptions`` | InternationalOptions, optional | Customs information
    that can be used to generate customs documents for international orders.  Use
    the [**InternationalOptions**](http://www.shipstation.com/developer-api/#/reference/model-internationaloptions)
    model.\n``advancedOptions`` | AdvancedOptions, optional | Various advanced options
    that may be available depending on the shipping carrier that is used to ship the
    order. Use the [**AdvancedOptions**](http://www.shipstation.com/developer-api/#/reference/model-advancedoptions)
    model."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/orderscreateorder-post-openapi.md
- name: Ship Station Developer Portal - Create/Update Multiple Orders
  x-api-slug: orderscreateorders-post
  description: |-
    This endpoint can be used to create or update multiple orders in one request. If the ``orderKey`` is specified in an order, the existing order with that key will be updated. Note: Only orders in an open status in ShipStation (``awaiting_payment``,``awaiting_shipment``, and ``on_hold``) can be updated through this method. ``cancelled`` and ``shipped`` are locked from modification through the API.

    Data Type          |Description
    -------------------|-------------------
    Order, required | An array of [**Order**](http://www.shipstation.com/developer-api/#/reference/model-order) objects (maximum of 100 per request)
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/orderscreateorders-post-openapi.md
- name: Ship Station Developer Portal - Hold Order Until
  x-api-slug: ordersholduntil-post
  description: |-
    This method will change the status of the given order to On Hold until the date specified, when the status will automatically change to Awaiting Shipment.

    The body of this request should specify the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
    ``orderId`` | number, required | Identifies the order that will be held.
    ``holdUntilDate`` | string, required | Date when order is moved from ``on_hold`` status to ``awaiting_shipment``.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/ordersholduntil-post-openapi.md
- name: Ship Station Developer Portal - List Orders by Tag
  x-api-slug: orderslistbytagorderstatusorderstatustagidtagidpagepagepagesizepagesize-get
  description: |-
    Lists all orders that match the specified status and tag ID.

    Url format with filters:

    ```
    /listbytag?orderStatus={orderStatus}
    &tagId={tagId}
    &page={page}
    &pageSize={pageSize}
    ```
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/orderslistbytagorderstatusorderstatustagidtagidpagepagepagesizepagesize-get-openapi.md
- name: Ship Station Developer Portal - Mark an Order as Shipped
  x-api-slug: ordersmarkasshipped-post
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/ordersmarkasshipped-post-openapi.md
- name: Ship Station Developer Portal - Remove Tag from Order
  x-api-slug: ordersremovetag-post
  description: |-
    Removes a tag from the specified order.  The body of this request has the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
    ``orderId`` | number, required | Identifies the order whose tag will be removed.
    ``tagId`` | number, required | Identifies the tag to remove.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/ordersremovetag-post-openapi.md
- name: Ship Station Developer Portal - Restore Order from On Hold
  x-api-slug: ordersrestorefromhold-post
  description: |-
    This method will change the status of the given order from On Hold to Awaiting Shipment. This endpoint is used when a holdUntil Date is attached to an order.

    The body of this request should specify the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
    ``orderId`` | number, required | Identifies the order that will be restored to ``awaiting_shipment`` from ``on_hold``.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/ordersrestorefromhold-post-openapi.md
- name: Ship Station Developer Portal - Unassign User from Order
  x-api-slug: ordersunassignuser-post
  description: |-
    Unassigns a user from an order.  The body of this request should specify the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
    ``orderIds`` | number, required | Identifies set of orders that will have the user unassigned.  Please note that if ANY of the orders within the array are not found, then no orders will have their users unassigned.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/ordersunassignuser-post-openapi.md
- name: Ship Station Developer Portal - Delete Order
  x-api-slug: ordersorderid-delete
  description: Removes order from ShipStation's UI. Note this is a "soft" delete action
    so the order will still exist in the database, but will be set to ``inactive``
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/ordersorderid-delete-openapi.md
- name: Ship Station Developer Portal - Get Order
  x-api-slug: ordersorderid-get
  description: Retrieves a single order from the database.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/ordersorderid-get-openapi.md
- name: Ship Station Developer Portal - List Orders with parameters
  x-api-slug: orderscustomernamecustomernameitemkeyworditemkeywordcreatedatestartcreatedatestartcreatedateendcreatedateendmodifydatestartmodifydatestartmodifydateendmodifydateendorderdatestartorderdatestartorderdateendorderdateend-get
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/orderscustomernamecustomernameitemkeyworditemkeywordcreatedatestartcreatedatestartcreatedateendcreatedateendmodifydatestartmodifydatestartmodifydateendmodifydateendorderdatestartorderdatestartorderdateendorderdateend-get-openapi.md
- name: Ship Station Developer Portal - List Products w/o parameters
  x-api-slug: products-get
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/products-get-openapi.md
- name: Ship Station Developer Portal - Get Product
  x-api-slug: productsproductid-get
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/productsproductid-get-openapi.md
- name: Ship Station Developer Portal - Update Product
  x-api-slug: productsproductid-put
  description: Updates an existing product. This call does not currently support partial
    updates. The entire resource must be provided in the body of the request.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/productsproductid-put-openapi.md
- name: Ship Station Developer Portal - List Products with parameters
  x-api-slug: productsskuskunamenameproductcategoryidproductcategoryidproducttypeidproducttypeidtagidtagidstartdatestartdateenddateenddateshowinactiveshowinactivesortbysortbysortdirsortdirpagepagepagesizepagesize-get
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/productsskuskunamenameproductcategoryidproductcategoryidproducttypeidproducttypeidtagidtagidstartdatestartdateenddateenddateshowinactiveshowinactivesortbysortbysortdirsortdirpagepagepagesizepagesize-get-openapi.md
- name: Ship Station Developer Portal - List Shipments w/o parameters
  x-api-slug: shipments-get
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/shipments-get-openapi.md
- name: Ship Station Developer Portal - Create Shipment Label
  x-api-slug: shipmentscreatelabel-post
  description: "Creates a shipping label.  The ``labelData`` field returned in the
    response is a base64 encoded PDF value. Simply decode and save the output as a
    PDF file to retrieve a printable label.  The body of this request has the following
    attributes:\n\nName               |Data Type          |Description\n-------------------|-------------------|-------------------\n
    ``carrierCode`` | string, required | Identifies the carrier to be used for this
    label.\n ``serviceCode`` | string, required | Identifies the shipping service
    to be used for this label.\n ``packageCode`` | string, required | Identifies the
    packing type that should be used for this label.\n ``confirmation`` | string,
    optional | Identifies the delivery confirmation type to be used for this label.\n
    ``shipDate`` | string, required | The date the shipment will be shipped.\n ``weight``
    | Weight, required | Shipment's weight.  Use the [**Weight**](https://www.shipstation.com/developer-api/#/reference/model-weight)
    model.\n ``dimensions`` | Dimensions, optional | Shipment's dimensions.  Use the
    [**Dimensions**](https://www.shipstation.com/developer-api/#/reference/model-dimensions)
    model.\n ``shipFrom`` | Address, required | Address indicating shipment's origin.
    \ Use the [**Address**](https://www.shipstation.com/developer-api/#/reference/model-address)
    model.\n ``shipTo`` | Address, required | Address indicating shipment's destination.
    \ Use the [**Address**](https://www.shipstation.com/developer-api/#/reference/model-address)
    model.\n ``insuranceOptions`` | InsuranceOptions, optional | The shipping insurance
    information associated with this order.  \n ``internationalOptions`` | InternationalOptions,
    optional | Customs information that can be used to generate customs documents
    for international orders.  Use the [**InternationalOptions**](https://www.shipstation.com/developer-api/#/reference/model-internationaloptions)
    model.\n ``advancedOptions`` | AdvancedOptions, optional | Various advanced options
    that may be available depending on the shipping carrier that is used to ship the
    order.  Use the [**AdvancedOptions**](https://www.shipstation.com/developer-api/#/reference/model-advancedoptions)
    model. \n ``testLabel`` | boolean, optional | Specifies whether a test label should
    be created. Default value: false."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/shipmentscreatelabel-post-openapi.md
- name: Ship Station Developer Portal - Get Rates
  x-api-slug: shipmentsgetrates-post
  description: "Retrieves shipping rates for the specified shipping details.  The
    body of this request should specify the following attributes:\n\nName               |Data
    Type          |Description\n-------------------|-------------------|-------------------\n
    ``carrierCode`` | string, required | Returns rates for the specified carrier.\n
    ``serviceCode`` | string, optional | Returns rates for the specified shipping
    service.\n ``packageCode`` | string, optional | Returns rates for the specified
    package type.\n ``fromPostalCode`` | string, required | Originating postal code.\n
    ``toState`` | string, optional | Destination State/Province. Please use two-character
    state/province abbreviation. Note this field is required for the following carriers:
    UPS\n ``toCountry`` | string, required | Destination Country.  Please use the
    two-character ISO country code.\n ``toPostalCode`` | string, required | Destination
    Postal Code.\n ``toCity`` | string, optional | Destination City.\n ``weight``
    | Weight, required | Shipment's weight.  Use ``Weight`` object.\n ``dimensions``
    | Dimensions, optional | Shipment's dimensions.  Use ``Dimensions`` object. \n
    ``confirmation`` | string, optional | Returns rates that account for the specified
    delivery confirmation type.\n ``residential`` | boolean, optional | Returns rates
    that account for the specified delivery confirmation type. Default value: false"
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/shipmentsgetrates-post-openapi.md
- name: Ship Station Developer Portal - Void Label
  x-api-slug: shipmentsvoidlabel-post
  description: |-
    Voids the specified label by shipmentId.  The body of this request should specify the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
     ``shipmentId`` | number, required | ID of the shipment to void.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/shipmentsvoidlabel-post-openapi.md
- name: Ship Station Developer Portal - List Shipments with parameters
  x-api-slug: shipmentsrecipientnamerecipientnamerecipientcountrycoderecipientcountrycodeordernumberordernumberorderidorderidcarriercodecarriercodeservicecodeservicecodetrackingnumbertrackingnumbercreatedatestartcreatedatestartcre-get
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/shipmentsrecipientnamerecipientnamerecipientcountrycoderecipientcountrycodeordernumberordernumberorderidorderidcarriercodecarriercodeservicecodeservicecodetrackingnumbertrackingnumbercreatedatestartcreatedatestartcre-get-openapi.md
- name: Ship Station Developer Portal - Deactivate Store
  x-api-slug: storesdeactivate-post
  description: |-
    Deactivates the specified store.

    The body of this request has the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
    ``storeId``  | number, required | ID of the store to deactivate.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/storesdeactivate-post-openapi.md
- name: Ship Station Developer Portal - Get Store Refresh Status
  x-api-slug: storesgetrefreshstatusstoreidstoreid-get
  description: Retrieves the refresh status of a given store.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/storesgetrefreshstatusstoreidstoreid-get-openapi.md
- name: Ship Station Developer Portal - List Marketplaces
  x-api-slug: storesmarketplaces-get
  description: Lists the marketplaces that can be integrated with ShipStation.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/storesmarketplaces-get-openapi.md
- name: Ship Station Developer Portal - Reactivate Store
  x-api-slug: storesreactivate-post
  description: |-
    Reactivates the specified store. Note: stores are active by default

    The body of this request has the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
    ``storeId``  | number, required | ID of the store to reactivate.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/storesreactivate-post-openapi.md
- name: Ship Station Developer Portal - Refresh Store
  x-api-slug: storesrefreshstorestoreidstoreidrefreshdaterefreshdate-post
  description: Initiates a store refresh.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/storesrefreshstorestoreidstoreidrefreshdaterefreshdate-post-openapi.md
- name: Ship Station Developer Portal - Get Store
  x-api-slug: storesstoreid-get
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/storesstoreid-get-openapi.md
- name: Ship Station Developer Portal - Update Store
  x-api-slug: storesstoreid-put
  description: Updates an existing store. This call does not currently support partial
    updates. The entire resource must be provided in the body of the request.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/storesstoreid-put-openapi.md
- name: Ship Station Developer Portal - List Stores
  x-api-slug: storesshowinactiveshowinactivemarketplaceidmarketplaceid-get
  description: Retrieve the list of installed stores on the account.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/storesshowinactiveshowinactivemarketplaceidmarketplaceid-get-openapi.md
- name: Ship Station Developer Portal - List Users
  x-api-slug: usersshowinactiveshowinactive-get
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/usersshowinactiveshowinactive-get-openapi.md
- name: Ship Station Developer Portal - List Warehouses
  x-api-slug: warehouses-get
  description: Retrieves a list of your Ship From Locations (formerly known as warehouses).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/warehouses-get-openapi.md
- name: Ship Station Developer Portal - Create Warehouse
  x-api-slug: warehousescreatewarehouse-post
  description: |-
    Adds a Ship From Location (formerly known as warehouse) to your account.  The body of this request should specify the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
     ``warehouseName`` | string, optional | Name of Ship From Location.
     ``originAddress`` | Address, required | The origin address.  Shipping rates will be calculated from this address.  Use the [**Address**](https://www.shipstation.com/developer-api/#/reference/model-address) model.
     ``returnAddress`` | Address, optional | The return address.  If a "returnAddress" is not specified, your "originAddress" will be used as your "returnAddress". Use the [**Address**](https://www.shipstation.com/developer-api/#/reference/model-address) model.
     ``isDefault`` | boolean, optional | Specifies whether or not this will be your default Ship From Location.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/warehousescreatewarehouse-post-openapi.md
- name: Ship Station Developer Portal - Get Warehouse
  x-api-slug: warehouseswarehouseid-get
  description: Returns a list of active Ship From Locations (formerly known as warehouses)
    on the ShipStation account. Warehouses are now called "Ship From Locations" in
    the UI.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/warehouseswarehouseid-get-openapi.md
- name: Ship Station Developer Portal - Update Warehouse
  x-api-slug: warehouseswarehouseid-put
  description: Updates an existing Ship From Location (formerly known as warehouse).
    This call does not currently support partial updates. The entire resource must
    be provided in the body of the request. If a "returnAddress" object is not specified,
    your "originAddress" will be used as your "returnAddress".
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/warehouseswarehouseid-put-openapi.md
- name: Ship Station Developer Portal - List Webhooks
  x-api-slug: webhooks-get
  description: Retrieves a list of registered webhooks for the account
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/webhooks-get-openapi.md
- name: Ship Station Developer Portal - Subscribe to Webhook
  x-api-slug: webhookssubscribe-post
  description: |-
    Subscribes to a specific type of webhook. If a ``store_id`` is passed in, the webhooks will only be triggered for that specific ``store_id``.
    The ``event`` type that is passed in will determine what type of webhooks will be sent.

    NOTE: Webhooks will be sent to the URL specified in the ``target_url``. The HTTP request will be sent via POST and will contain a [**webhook JSON object**](https://www.shipstation.com/developer-api/#/reference/model-webhook) in the body.

    The body of this request to subscribe has the following attributes:

    Name               |Data Type          |Description
    -------------------|-------------------|-------------------
    ``target_url``  | string, required | The URL to send the webhooks to
    ``event`` | string, required | The type of webhook to subscribe to. Must contain one of the following values: ORDER_NOTIFY, ITEM_ORDER_NOTIFY, SHIP_NOTIFY, ITEM_SHIP_NOTIFY
    ``store_id`` | int, optional | If passed in, the webhooks will only be triggered for this ``store_id``
    ``friendly_name`` | string, optional | Display name for the webhook
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/webhookssubscribe-post-openapi.md
- name: Ship Station Developer Portal - Unsubscribe to Webhook
  x-api-slug: webhookswebhookid-delete
  description: Unsubscribes from a certain webhook.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/ShipStation-stacked-blue.png
  humanURL: http://bit.ly/_ShipStation
  baseURL: https://ssapi.shipstation.com//
  tags: Shipping, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ship-station/master/_listings/ship-station/webhookswebhookid-delete-openapi.md
x-common:
- type: x-website
  url: http://bit.ly/_ShipStation
- type: x-api-gallery
  url: http://server.density.api.gallery.streamdata.io
- type: x-api-stack
  url: http://ship.station.stack.network
- type: x-blog
  url: https://www.shipstation.com/blog/
- type: x-developer
  url: https://shipstation.docs.apiary.io/#
- type: x-github
  url: https://github.com/shipstation
- type: x-partners
  url: https://www.shipstation.com/partners/
- type: x-pricing
  url: https://www.shipstation.com/pricing/
- type: x-twitter
  url: https://twitter.com/ShipStation
- type: x-website
  url: http://shipstation.com
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---