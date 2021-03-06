This section details about the REST services in Commons Packet Manager.

# Packet Reader APIs
These services are used by registration processor to read data from a packet,
* Get Audits
* Get Biometrics
* Get Documents
* Get Meta Info
* Search Field
* Search Fields
* Validate Packet

## Get Audits
API to fetch the audit details from a packet.

### Resource URL
`POST https://{base_url}/commons/v1/packetmanager/audits`

### Resource details
Resource Details | Description
------------ | ----------------
Response format | JSON
Requires Authentication | Yes

### Request Body Parameters
Name | Required | Description 
-----|----------|------------
id | Y | ID for the API.
metadata | N | Meta Data for the API.
requesttime | Y | Request time for the API.
version | Y | Version for the API.
request.bypassCache | Y | Used to fetch data from cache or from object store.
request.id | Y | ID of the Packet.
request.process | Y | Process of the Packet.
request.source | Y | Source of the Packet.

### Request
```JSON
{
  "id": "string",
  "metadata": {},
  "request": {
    "bypassCache": true,
    "id": "string",
    "process": "string",
    "source": "string"
  },
  "requesttime": "2018-12-10T06:12:52.994Z",
  "version": "string"
}
```


### Response

#### Success Response
**Response Code : 200 (OK)**
```JSON
{
  "errors": [
    {
      "errorCode": "string",
      "message": "string"
    }
  ],
  "id": "string",
  "metadata": {},
  "response": [
    {
      "fields": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      }
    }
  ],
  "responsetime": "yyyy-MM-dd'T'HH:mm:ss.SSS'Z'",
  "version": "string"
}
```

#### Failure Response
**Response Code : 200 (OK)**
```JSON
{
  "id": null,
  "version": null,
  "responsetime": "2020-09-02T08:21:16.891Z",
  "metadata": null,
  "response": null,
  "errors": [
    {
      "errorCode": "KER-ATH-401",
      "message": "Authentication Failed"
    }
  ]
}
```

### Failure Details
Error Code | Message | Scenario
-----------|---------|---------
KER-ATH-401 | Authentication Failed | Authentication Failure


## Get Biometrics
API to fetch the biometric details from a packet.

### Resource URL
`POST https://{base_url}/commons/v1/packetmanager/biometrics`

### Resource details
Resource Details | Description
------------ | -------------
Response format | JSON
Requires Authentication | Yes

### Request Body Parameters
Name | Required | Description 
-----|----------|-------------
id | Y | ID of the API.
metadata | N | Metadata of the API.
requesttime | Y | Request time of the API.
version | Y | Version of the API.
request.bypassCache | Used to fetch data from cache or from object store.
request.id | Y | ID of the Packet.
request.modalities | Modalities of biometrics to be fetched.
request.person | Entity for whom the biometrics is to be fetched.
request.process | Process of the Packet.
request.source | Source of the Packet.

### Request
```JSON
{
  "id": "string",
  "metadata": {},
  "request": {
    "bypassCache": true,
    "id": "string",
    "modalities": [
      "SCENT"
    ],
    "person": "string",
    "process": "string",
    "source": "string"
  },
  "requesttime": "2018-12-10T06:12:52.994Z",
  "version": "string"
}
```


### Response

#### Success Response
**Response Code : 200 (OK)**
```JSON
{
  "errors": [
    {
      "errorCode": "string",
      "message": "string"
    }
  ],
  "id": "string",
  "metadata": {},
  "response": {
    "birInfo": {
      "creationDate": "2020-09-02T08:25:54.998Z",
      "creator": "string",
      "index": "string",
      "integrity": true,
      "notValidAfter": "2020-09-02T08:25:54.998Z",
      "notValidBefore": "2020-09-02T08:25:54.998Z",
      "payload": "string"
    },
    "cbeffversion": {
      "major": 0,
      "minor": 0
    },
    "segments": [
      {
        "bdb": "string",
        "bdbInfo": {
          "captureDevice": {
            "organization": "string",
            "type": "string"
          },
          "challengeResponse": "string",
          "comparisonAlgorithm": {
            "organization": "string",
            "type": "string"
          },
          "compressionAlgorithm": {
            "organization": "string",
            "type": "string"
          },
          "creationDate": "2020-09-02T08:25:54.998Z",
          "encryption": true,
          "featureExtractionAlgorithm": {
            "organization": "string",
            "type": "string"
          },
          "format": {
            "organization": "string",
            "type": "string"
          },
          "index": "string",
          "level": "RAW",
          "notValidAfter": "2020-09-02T08:25:54.998Z",
          "notValidBefore": "2020-09-02T08:25:54.998Z",
          "product": {
            "organization": "string",
            "type": "string"
          },
          "purpose": "VERIFY",
          "quality": {
            "algorithm": {
              "organization": "string",
              "type": "string"
            },
            "qualityCalculationFailed": "string",
            "score": 0
          },
          "subtype": [
            "string"
          ],
          "type": [
            "SCENT"
          ]
        },
        "birInfo": {
          "creationDate": "2020-09-02T08:25:54.998Z",
          "creator": "string",
          "index": "string",
          "integrity": true,
          "notValidAfter": "2020-09-02T08:25:54.998Z",
          "notValidBefore": "2020-09-02T08:25:54.998Z",
          "payload": "string"
        },
        "cbeffversion": {
          "major": 0,
          "minor": 0
        },
        "element": [
          {
            "globalScope": true,
            "name": {
              "localPart": "string",
              "namespaceURI": "string",
              "prefix": "string"
            },
            "nil": true,
            "typeSubstituted": true,
            "value": "string"
          }
        ],
        "sb": "string",
        "sbInfo": {
          "format": {
            "organization": "string",
            "type": "string"
          }
        },
        "version": {
          "major": 0,
          "minor": 0
        }
      }
    ],
    "version": {
      "major": 0,
      "minor": 0
    }
  },
  "responsetime": "yyyy-MM-dd'T'HH:mm:ss.SSS'Z'",
  "version": "string"
}
```

#### Failure Response
**Response Code : 200 (OK)**
```JSON
{
  "id": null,
  "version": null,
  "responsetime": "2020-09-02T08:21:16.891Z",
  "metadata": null,
  "response": null,
  "errors": [
    {
      "errorCode": "KER-ATH-401",
      "message": "Authentication Failed"
    }
  ]
}
```

### Failure Details
Error Code | Message | Scenario
-----------|---------|---------
KER-ATH-401 | Authentication Failed | Authentication Failure

## Get Documents

### Resource URL
`POST https://{base_url}/commons/v1/packetmanager/document`

### Resource details
Resource Details | Description
------------ | -------------
Response format | JSON
Requires Authentication | Yes

### Request Body Parameters
Name | Required | Description 
-----|----------|-------------
id | Y | ID of the API.
metadata | N | Metadata of the API.
requesttime | Y | Request time of the API.
version | Y | Version of the API.
request.documentName | Y | Name of the document to be fetched.
request.id | Y | ID of the Packet.
request.process | Y | Process of the Packet.
request.source | Y | Source of the Packet.

### Request
```JSON
{
  "id": "string",
  "metadata": {},
  "request": {
    "documentName": "string",
    "id": "string",
    "process": "string",
    "source": "string"
  },
  "requesttime": "2018-12-10T06:12:52.994Z",
  "version": "string"
}
```

### Response

#### Success Response
**Response Code : 200 (OK)**
```JSON
{
  "errors": [
    {
      "errorCode": "string",
      "message": "string"
    }
  ],
  "id": "string",
  "metadata": {},
  "response": {
    "document": "string",
    "format": "string",
    "type": "string",
    "value": "string"
  },
  "responsetime": "yyyy-MM-dd'T'HH:mm:ss.SSS'Z'",
  "version": "string"
}
```

#### Failure Response
**Response Code : 200 (OK)**
```JSON
{
  "id": null,
  "version": null,
  "responsetime": "2020-09-02T08:21:16.891Z",
  "metadata": null,
  "response": null,
  "errors": [
    {
      "errorCode": "KER-ATH-401",
      "message": "Authentication Failed"
    }
  ]
}
```

### Failure Details
Error Code | Message | Scenario
-----------|---------|---------
KER-ATH-401 | Authentication Failed | Authentication Failure

## Get Meta Info

### Resource URL
`POST https://{base_url}/commons/v1/packetmanager/metaInfo`

### Resource details
Resource Details | Description
------------ | -------------
Response format | JSON
Requires Authentication | Yes

### Request Body Parameters
Name | Required | Description 
-----|----------|-------------
id | Y | ID of the API.
metadata | N | Metadata of the API.
requesttime | Y | Request time of the API.
version | Y | Version of the API.
request.bypassCache | Y | Used to fetch data from cache or from object store.
request.id | Y | ID of the Packet.
request.process | Y | Process of the Packet.
request.source | Y | Source of the Packet.

### Request
```JSON
{
  "id": "string",
  "metadata": {},
  "request": {
    "bypassCache": true,
    "id": "string",
    "process": "string",
    "source": "string"
  },
  "requesttime": "2018-12-10T06:12:52.994Z",
  "version": "string"
}
```

### Response

#### Success Response
**Response Code : 200 (OK)**
```JSON
{
  "errors": [
    {
      "errorCode": "string",
      "message": "string"
    }
  ],
  "id": "string",
  "metadata": {},
  "response": {
    "fields": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    }
  },
  "responsetime": "yyyy-MM-dd'T'HH:mm:ss.SSS'Z'",
  "version": "string"
}
```

#### Failure Response
**Response Code : 200 (OK)**
```JSON
{
  "id": null,
  "version": null,
  "responsetime": "2020-09-02T08:21:16.891Z",
  "metadata": null,
  "response": null,
  "errors": [
    {
      "errorCode": "KER-ATH-401",
      "message": "Authentication Failed"
    }
  ]
}
```

### Failure Details
Error Code | Message | Scenario
-----------|---------|---------
KER-ATH-401 | Authentication Failed | Authentication Failure

## Search Field

### Resource URL
`POST https://{base_url}/commons/v1/packetmanager/searchField`

### Resource details
Resource Details | Description
------------ | -------------
Response format | JSON
Requires Authentication | Yes

### Request Body Parameters
Name | Required | Description 
-----|----------|-------------
id | Y | ID of the API.
metadata | N | Metadata of the API.
requesttime | Y | Request time of the API.
version | Y | Version of the API.
request.bypassCache | Y | Used to fetch data from cache or from object store.
request.field | Y | Field Name for which data needs to be fetched.
request.id | Y | ID of the Packet.
request.process | Y | Process of the Packet.
request.source | Y | Source of the Packet.

### Request
```JSON
{
  "id": "string",
  "metadata": {},
  "request": {
    "bypassCache": true,
    "field": "string",
    "id": "string",
    "process": "string",
    "source": "string"
  },
  "requesttime": "2018-12-10T06:12:52.994Z",
  "version": "string"
}
```

### Response

#### Success Response
**Response Code : 200 (OK)**
```JSON
{
  "errors": [
    {
      "errorCode": "string",
      "message": "string"
    }
  ],
  "id": "string",
  "metadata": {},
  "response": {
    "fields": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    }
  },
  "responsetime": "yyyy-MM-dd'T'HH:mm:ss.SSS'Z'",
  "version": "string"
}
```

#### Failure Response
**Response Code : 200 (OK)**
```JSON
{
  "id": null,
  "version": null,
  "responsetime": "2020-09-02T08:21:16.891Z",
  "metadata": null,
  "response": null,
  "errors": [
    {
      "errorCode": "KER-ATH-401",
      "message": "Authentication Failed"
    }
  ]
}
```

### Failure Details
Error Code | Message | Scenario
-----------|---------|---------
KER-ATH-401 | Authentication Failed | Authentication Failure

## Search Fields

### Resource URL
`POST https://{base_url}/commons/v1/packetmanager/searchFields`

### Resource details
Resource Details | Description
------------ | -------------
Response format | JSON
Requires Authentication | Yes

### Request Body Parameters
Name | Required | Description 
-----|----------|-------------
id | Y | ID of the API.
metadata | Y | Metadata of the API.
requesttime | Y | Request time of the API.
version | Y | Version of the API.
request.bypassCache | Y | Used to fetch data from cache or from object store.
request.fields | Y | List of fields to be fetched.
request.id | Y | ID of the Packet.
request.process | Y | Process of the Packet.
request.source | Y | Source of the Packet.

### Request
```JSON
{
  "id": "string",
  "metadata": {},
  "request": {
    "bypassCache": true,
    "fields": [
      "string"
    ],
    "id": "string",
    "process": "string",
    "source": "string"
  },
  "requesttime": "2018-12-10T06:12:52.994Z",
  "version": "string"
}
```

### Response

#### Success Response
**Response Code : 200 (OK)**
```JSON
{
  "errors": [
    {
      "errorCode": "string",
      "message": "string"
    }
  ],
  "id": "string",
  "metadata": {},
  "response": {
    "fields": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    }
  },
  "responsetime": "yyyy-MM-dd'T'HH:mm:ss.SSS'Z'",
  "version": "string"
}
```

#### Failure Response
**Response Code : 200 (OK)**
```JSON
{
  "id": null,
  "version": null,
  "responsetime": "2020-09-02T08:21:16.891Z",
  "metadata": null,
  "response": null,
  "errors": [
    {
      "errorCode": "KER-ATH-401",
      "message": "Authentication Failed"
    }
  ]
}
```

### Failure Details
Error Code | Message | Scenario
-----------|---------|---------
KER-ATH-401 | Authentication Failed | Authentication Failure

## Validate Packet

### Resource URL
`POST https://{base_url}/commons/v1/packetmanager/searchFields`

### Resource details
Resource Details | Description
------------ | -------------
Response format | JSON
Requires Authentication | Yes

### Request Body Parameters
Name | Required | Description 
-----|----------|-------------
id | Y | ID of the API.
metadata | N | Metadata of the API.
requesttime | Y | Request time of the API.
version | Y | Version of the API.
request.bypassCache | Y | Used to fetch data from cache or from object store.
request.id | Y | ID of the Packet.
request.process | Y | Process of the Packet.
request.source | Y | Source of the Packet.

### Request
```JSON
{
  "id": "string",
  "metadata": {},
  "request": {
    "bypassCache": true,
    "id": "string",
    "process": "string",
    "source": "string"
  },
  "requesttime": "2018-12-10T06:12:52.994Z",
  "version": "string"
}
```

### Response

#### Success Response
**Response Code : 200 (OK)**
```JSON
{
  "errors": [
    {
      "errorCode": "string",
      "message": "string"
    }
  ],
  "id": "string",
  "metadata": {},
  "response": {
    "valid": true
  },
  "responsetime": "yyyy-MM-dd'T'HH:mm:ss.SSS'Z'",
  "version": "string"
}
```

#### Failure Response
**Response Code : 200 (OK)**
```JSON
{
  "id": null,
  "version": null,
  "responsetime": "2020-09-02T08:21:16.891Z",
  "metadata": null,
  "response": null,
  "errors": [
    {
      "errorCode": "KER-ATH-401",
      "message": "Authentication Failed"
    }
  ]
}
```

### Failure Details
Error Code | Message | Scenario
-----------|---------|---------
KER-ATH-401 | Authentication Failed | Authentication Failure


# Packet Writer API
This service is used to create a packet in Registration Processor.

## Create Packet

### Resource URL
`PUT https://{base_url}/commons/v1/packetmanager/searchFields`

### Resource details
Resource Details | Description
------------ | -------------
Response format | JSON
Requires Authentication | Yes

### Request Body Parameters
Name | Required | Description 
-----|----------|-------------
id | Y | ID of the API.
metadata | N | Metadata of the API.
requesttime | Y | Request time of the API.
version | Y | Version of the API.
request.audits | Y | Audit trail of the packet.
request.biometrics | N | Biometrics in the packet.
request.documents | N | Documents in the packet.
request.id | Y | ID of the packet.
request.fields | Y | Fields in the packet.
request.metaInfo | Y | Metainfo of the packet.
request.schemaJson | Y | Schema JSON to use inorder to create the Packet.
request.schemaVersion | Y | Schema Version to use inorder to create the Packet.
request.process | Y | Process of the Packet.
request.source | Y | Source of the Packet.

### Request
```JSON
{
  "id": "string",
  "metadata": {},
  "request": {
    "audits": [
      {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      }
    ],
    "biometrics": {
      "additionalProp1": {
        "birInfo": {
          "creationDate": "2020-09-02T08:48:03.518Z",
          "creator": "string",
          "index": "string",
          "integrity": true,
          "notValidAfter": "2020-09-02T08:48:03.519Z",
          "notValidBefore": "2020-09-02T08:48:03.519Z",
          "payload": "string"
        },
        "cbeffversion": {
          "major": 0,
          "minor": 0
        },
        "segments": [
          {
            "bdb": "string",
            "bdbInfo": {
              "captureDevice": {
                "organization": "string",
                "type": "string"
              },
              "challengeResponse": "string",
              "comparisonAlgorithm": {
                "organization": "string",
                "type": "string"
              },
              "compressionAlgorithm": {
                "organization": "string",
                "type": "string"
              },
              "creationDate": "2020-09-02T08:48:03.519Z",
              "encryption": true,
              "featureExtractionAlgorithm": {
                "organization": "string",
                "type": "string"
              },
              "format": {
                "organization": "string",
                "type": "string"
              },
              "index": "string",
              "level": "RAW",
              "notValidAfter": "2020-09-02T08:48:03.519Z",
              "notValidBefore": "2020-09-02T08:48:03.519Z",
              "product": {
                "organization": "string",
                "type": "string"
              },
              "purpose": "VERIFY",
              "quality": {
                "algorithm": {
                  "organization": "string",
                  "type": "string"
                },
                "qualityCalculationFailed": "string",
                "score": 0
              },
              "subtype": [
                "string"
              ],
              "type": [
                "SCENT"
              ]
            },
            "birInfo": {
              "creationDate": "2020-09-02T08:48:03.519Z",
              "creator": "string",
              "index": "string",
              "integrity": true,
              "notValidAfter": "2020-09-02T08:48:03.519Z",
              "notValidBefore": "2020-09-02T08:48:03.519Z",
              "payload": "string"
            },
            "cbeffversion": {
              "major": 0,
              "minor": 0
            },
            "element": [
              {
                "globalScope": true,
                "name": {
                  "localPart": "string",
                  "namespaceURI": "string",
                  "prefix": "string"
                },
                "nil": true,
                "typeSubstituted": true,
                "value": "string"
              }
            ],
            "sb": "string",
            "sbInfo": {
              "format": {
                "organization": "string",
                "type": "string"
              }
            },
            "version": {
              "major": 0,
              "minor": 0
            }
          }
        ],
        "version": {
          "major": 0,
          "minor": 0
        }
      }
    },
    "documents": {
      "additionalProp1": {
        "document": "string",
        "format": "string",
        "type": "string",
        "value": "string"
      }
    },
    "fields": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    },
    "id": "string",
    "metaInfo": {
      "additionalProp1": "string",
      "additionalProp2": "string",
      "additionalProp3": "string"
    },
    "process": "string",
    "schemaJson": "string",
    "schemaVersion": "string",
    "source": "string"
  },
  "requesttime": "2018-12-10T06:12:52.994Z",
  "version": "string"
}
```

### Response

#### Success Response
**Response Code : 200 (OK)**
```JSON
{
  "errors": [
    {
      "errorCode": "string",
      "message": "string"
    }
  ],
  "id": "string",
  "metadata": {},
  "response": [
    {
      "creationDate": "string",
      "encryptedHash": "string",
      "id": "string",
      "packetName": "string",
      "process": "string",
      "providerName": "string",
      "providerVersion": "string",
      "schemaVersion": "string",
      "signature": "string",
      "source": "string"
    }
  ],
  "responsetime": "yyyy-MM-dd'T'HH:mm:ss.SSS'Z'",
  "version": "string"
}
```

#### Failure Response
**Response Code : 200 (OK)**
```JSON
{
  "id": null,
  "version": null,
  "responsetime": "2020-09-02T08:21:16.891Z",
  "metadata": null,
  "response": null,
  "errors": [
    {
      "errorCode": "KER-ATH-401",
      "message": "Authentication Failed"
    }
  ]
}
```

### Failure Details
Error Code | Message | Scenario
-----------|---------|---------
KER-ATH-401 | Authentication Failed | Authentication Failure

