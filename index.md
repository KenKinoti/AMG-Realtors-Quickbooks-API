# AMG Realtors 

## Quickbooks API Documentation
A documenation for the API's avalable for AMG Relators Quickbooks API Integration

### Allowed HTTP Requests
- POST    : Update resource
- GET     : Get a resource or list of resources

### Description Of Usual Server Responses:
- 200 OK - the request was successful (some API calls may return 201 instead).
- 201 Created - the request was successful and a resource was created.
- 204 No Content - the request was successful but there is no representation to return (i.e. the response is empty).
- 400 Bad Request - the request could not be understood or was missing required parameters.
- 401 Unauthorized - authentication failed or user doesn't have permissions for requested operation.
- 403 Forbidden - access denied.
- 404 Not Found - resource was not found.


## Endpoint Samples

### GET : Ping
Request 

>GET : https://quickbooks-api-239414.appspot.com/

Success Response
```
{
      "message": "Welcome to AMG Realtors API"
}
```

Error Response
```
{
      "message": "Error with ping endpoint"
}
```

### GET : Customers
Request

> GET : https://quickbooks-api-239414.appspot.com/customers


Success Response
```
{  
   "QueryResponse":{  
      "Customer":[  
         {  
            "Balance":239,
            "sparse":true,
            "Id":"1",
            "GivenName":"Amy",
            "FamilyName":"Lauterbach"
         }
      ],
      "startPosition":1,
      "maxResults":29
   },
   "time":"2019-05-09T06:05:28.747-07:00"
}
```

Error Response
```
{
      "message": "Error with customer API"
}
```
### POST : Payment-Update

Request

> POST : COMING SOON


Headers
```
User-Agent	{{UserAgent}}
Accept	application/json
Content-Type	application/json
```

Params
```
minorversion	{{minorversion}}
```

Body
```
{
    "CustomerRef": {
      "value": "58",
      "name": "TEST123"
    },
    "DepositToAccountRef": {
      "value": "4"
    },
    "TotalAmt": 100,
    "UnappliedAmt": 0,
    "ProcessPayment": false,
    "domain": "QBO",
    "sparse": false,
    "Id": "174",
    "SyncToken": "0",
    "TxnDate": "2016-08-29",
    "CurrencyRef": {
      "value": "USD",
      "name": "United States Dollar"
    },
    "ExchangeRate": 1,
    "Line": [
      {
        "Amount": 100,
        "LinkedTxn": [
          {
            "TxnId": "173",
            "TxnType": "Invoice"
          }
        ],
        "LineEx": {
          "any": [
            {
              "name": "{http://schema.intuit.com/finance/v3}NameValue",
              "declaredType": "com.intuit.schema.finance.v3.NameValue",
              "scope": "javax.xml.bind.JAXBElement$GlobalScope",
              "value": {
                "Name": "txnReferenceNumber",
                "Value": "1043"
              },
              "nil": false,
              "globalScope": true,
              "typeSubstituted": false
            }
          ]
        }
      }
    ]
  }
  ```
