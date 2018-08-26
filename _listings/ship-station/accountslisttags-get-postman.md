{
  "info": {
    "name": "Ship Station List Tags",
    "_postman_id": "18d489e7-195f-4241-adf8-339dd1c9cd0c",
    "description": "Lists all tags defined for this account.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "List",
      "item": [
        {
          "id": "90b5a08b-e8ad-455f-9d62-84cf74d80754",
          "name": "accounts.listtags.get",
          "request": {
            "url": "http://ssapi.shipstation.com/accounts/listtags",
            "method": "GET",
            "header": [
              {
                "key": "Accept",
                "value": "*/*",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "Lists all tags defined for this account."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "94f80a50-d1b8-4356-b77b-6ad7b319d09d"
            }
          ]
        }
      ]
    }
  ]
}