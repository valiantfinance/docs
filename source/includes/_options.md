# Options

🎛

Our Options API is used to provide accepted values for a number of attributes across various resources.

<aside class="notice">
  ⚠️ The values returned from these endpoints, and thus the accepted values, may change at anytime. We highly recommend using these endpoints to generate the list of valid options for your end user to select.
</aside>

## Accounting Software

| Item              | Details                                                            |
| ----------------- | -------------------------------------------------------            |
| Endpoint          | `/api/v1/options/accounting_software`                              |
| Supported methods | `GET`                                                              |
| Description       | Returns a collection of accounting software label and value pairs. |


### Corresponding Attributes

| Resource          | Attribute                                                  |
| ----------------- | -------------------------------------------------------    |
| [Lead](#leads)    | `accounting_software`                                          |



### Response

> Example request

```javascript
xhr = new XMLHttpRequest();

xhr.open("GET", "https://valiant.finance/api/v1/options/accounting_software");
xhr.setRequestHeader("X-AUTH-ID",         "<API_ID>")
xhr.setRequestHeader("X-AUTH-SIGNED-KEY", "<API_SIGNED_KEY>");
xhr.setRequestHeader("Content-Type",      "application/vnd.api+json");

xhr.onreadystatechange = function () {
  if (xhr.readyState == 4) {
    console.log(xhr.status);
    console.log(xhr.responseText);
  }
}

xhr.send();
```

```jquery

$.ajax({
  url: "https://valiant.finance/api/v1/options/accounting_software",
  type: "GET",
  contentType: "application/vnd.api+json",
  headers: {
    "X-AUTH-ID":         "<API_ID>",
    "X-AUTH-SIGNED-KEY": "<API_SIGNED_KEY>",
    "Content-Type":      "application/vnd.api+json"
  },

  beforeSend: function(data) {
    console.log("beforeSend");
  },

  success: function(data) {
    console.log("success");
    console.log(data);
  },

  error: function(data) {
    console.log("error");
  },

  complete: function(data) {
    console.log("complete!");
  }
});
```

```bash
curl -iX GET \
  https://valiant.finance/api/v1/options/accounting_software \
  -H "X-AUTH-ID:         <API_ID>" \
  -H "X-AUTH-SIGNED-KEY: <API_SIGNED_KEY>" \
  -H "Content-Type:      application/vnd.api+json"
```

> Example successful response

If a request is successful, a JSON response will include a collection of valid options, with an option in the format <code>{ "label": "Example Label", "value": "example_value" }</code> where the label component can be used for display purposes, and the value component as the accepted value.

```json
{
    "label": "Example Label", "value": "example_value"
}
```

## Australian State

| Item              | Details                                                         |
| ----------------- | -------------------------------------------------------         |
| Endpoint          | `/api/v1/options/australian_state`                              |
| Supported methods | `GET`                                                           |
| Description       | Returns a collection of Australian state label and value pairs. |


### Corresponding Attributes

| Resource          | Attribute                                                  |
| ----------------- | -------------------------------------------------------    |
| [Lead](#leads)    | `australian_state`                                         |



### Response

> Example request

```javascript
xhr = new XMLHttpRequest();

xhr.open("GET", "https://valiant.finance/api/v1/options/australian_state");
xhr.setRequestHeader("X-AUTH-ID",         "<API_ID>")
xhr.setRequestHeader("X-AUTH-SIGNED-KEY", "<API_SIGNED_KEY>");
xhr.setRequestHeader("Content-Type",      "application/vnd.api+json");

xhr.onreadystatechange = function () {
  if (xhr.readyState == 4) {
    console.log(xhr.status);
    console.log(xhr.responseText);
  }
}

xhr.send();
```

```jquery

$.ajax({
  url: "https://valiant.finance/api/v1/options/australian_state",
  type: "GET",
  contentType: "application/vnd.api+json",
  headers: {
    "X-AUTH-ID":         "<API_ID>",
    "X-AUTH-SIGNED-KEY": "<API_SIGNED_KEY>",
    "Content-Type":      "application/vnd.api+json"
  },

  beforeSend: function(data) {
    console.log("beforeSend");
  },

  success: function(data) {
    console.log("success");
    console.log(data);
  },

  error: function(data) {
    console.log("error");
  },

  complete: function(data) {
    console.log("complete!");
  }
});
```

```bash
curl -iX GET \
  https://valiant.finance/api/v1/options/australian_state \
  -H "X-AUTH-ID:         <API_ID>" \
  -H "X-AUTH-SIGNED-KEY: <API_SIGNED_KEY>" \
  -H "Content-Type:      application/vnd.api+json"
```

> Example successful response

If a request is successful, a JSON response will include a collection of valid options, with an option in the format <code>{ "label": "Example Label", "value": "example_value" }</code> where the label component can be used for display purposes, and the value component as the accepted value.

```json
{
    "label": "Example Label", "value": "example_value"
}
```

## Business Performance

| Item              | Details                                                            |
| ----------------- | -------------------------------------------------------            |
| Endpoint          | `/api/v1/options/business_performance`                             |
| Supported methods | `GET`                                                              |
| Description       | Returns a collection of business performance label and value pairs.|


### Corresponding Attributes

| Resource          | Attribute                                                  |
| ----------------- | -------------------------------------------------------    |
| [Lead](#leads)    | `business_performance`                                     |


### Response

> Example request

```javascript
xhr = new XMLHttpRequest();

xhr.open("GET", "https://valiant.finance/api/v1/options/business_performance");
xhr.setRequestHeader("X-AUTH-ID",         "<API_ID>")
xhr.setRequestHeader("X-AUTH-SIGNED-KEY", "<API_SIGNED_KEY>");
xhr.setRequestHeader("Content-Type",      "application/vnd.api+json");

xhr.onreadystatechange = function () {
  if (xhr.readyState == 4) {
    console.log(xhr.status);
    console.log(xhr.responseText);
  }
}

xhr.send();
```

```jquery

$.ajax({
  url: "https://valiant.finance/api/v1/options/business_performance",
  type: "GET",
  contentType: "application/vnd.api+json",
  headers: {
    "X-AUTH-ID":         "<API_ID>",
    "X-AUTH-SIGNED-KEY": "<API_SIGNED_KEY>",
    "Content-Type":      "application/vnd.api+json"
  },

  beforeSend: function(data) {
    console.log("beforeSend");
  },

  success: function(data) {
    console.log("success");
    console.log(data);
  },

  error: function(data) {
    console.log("error");
  },

  complete: function(data) {
    console.log("complete!");
  }
});
```

```bash
curl -iX GET \
  https://valiant.finance/api/v1/options/business_performance \
  -H "X-AUTH-ID:         <API_ID>" \
  -H "X-AUTH-SIGNED-KEY: <API_SIGNED_KEY>" \
  -H "Content-Type:      application/vnd.api+json"
```

> Example successful response

If a request is successful, a JSON response will include a collection of valid options, with an option in the format <code>{ "label": "Example Label", "value": "example_value" }</code> where the label component can be used for display purposes, and the value component as the accepted value.

```json
{
    "label": "Example Label", "value": "example_value"
}
```

## Credit Status

| Item              | Details                                                     |
| ----------------- | -------------------------------------------------------     |
| Endpoint          | `/api/v1/options/credit_status`                             |
| Supported methods | `GET`                                                       |
| Description       | Returns a collection of credit status label and value pairs.|


### Corresponding Attributes

| Resource          | Attribute                                                  |
| ----------------- | -------------------------------------------------------    |
| [Lead](#leads)    | `credit_status`                                            |



### Response

> Example request

```javascript
xhr = new XMLHttpRequest();

xhr.open("GET", "https://valiant.finance/api/v1/options/credit_status");
xhr.setRequestHeader("X-AUTH-ID",         "<API_ID>")
xhr.setRequestHeader("X-AUTH-SIGNED-KEY", "<API_SIGNED_KEY>");
xhr.setRequestHeader("Content-Type",      "application/vnd.api+json");

xhr.onreadystatechange = function () {
  if (xhr.readyState == 4) {
    console.log(xhr.status);
    console.log(xhr.responseText);
  }
}

xhr.send();
```

```jquery

$.ajax({
  url: "https://valiant.finance/api/v1/options/credit_status",
  type: "GET",
  contentType: "application/vnd.api+json",
  headers: {
    "X-AUTH-ID":         "<API_ID>",
    "X-AUTH-SIGNED-KEY": "<API_SIGNED_KEY>",
    "Content-Type":      "application/vnd.api+json"
  },

  beforeSend: function(data) {
    console.log("beforeSend");
  },

  success: function(data) {
    console.log("success");
    console.log(data);
  },

  error: function(data) {
    console.log("error");
  },

  complete: function(data) {
    console.log("complete!");
  }
});
```

```bash
curl -iX GET \
  https://valiant.finance/api/v1/options/credit_status \
  -H "X-AUTH-ID:         <API_ID>" \
  -H "X-AUTH-SIGNED-KEY: <API_SIGNED_KEY>" \
  -H "Content-Type:      application/vnd.api+json"
```

> Example successful response

If a request is successful, a JSON response will include a collection of valid options, with an option in the format <code>{ "label": "Example Label", "value": "example_value" }</code> where the label component can be used for display purposes, and the value component as the accepted value.

```json
{
    "label": "Example Label", "value": "example_value"
}
```

## Entity Type

| Item              | Details                                                            |
| ----------------- | -------------------------------------------------------            |
| Endpoint          | `/api/v1/options/entity_type`                                      |
| Supported methods | `GET`                                                              |
| Description       | Returns a collection of entity type label and value pairs.         |


### Corresponding Attributes

| Resource          | Attribute                                                      |
| ----------------- | -------------------------------------------------------        |
| [Lead](#leads)    | `entity_type`                                          |



### Response

> Example request

```javascript
xhr = new XMLHttpRequest();

xhr.open("GET", "https://valiant.finance/api/v1/options/entity_type");
xhr.setRequestHeader("X-AUTH-ID",         "<API_ID>")
xhr.setRequestHeader("X-AUTH-SIGNED-KEY", "<API_SIGNED_KEY>");
xhr.setRequestHeader("Content-Type",      "application/vnd.api+json");

xhr.onreadystatechange = function () {
  if (xhr.readyState == 4) {
    console.log(xhr.status);
    console.log(xhr.responseText);
  }
}

xhr.send();
```

```jquery

$.ajax({
  url: "https://valiant.finance/api/v1/options/entity_type",
  type: "GET",
  contentType: "application/vnd.api+json",
  headers: {
    "X-AUTH-ID":         "<API_ID>",
    "X-AUTH-SIGNED-KEY": "<API_SIGNED_KEY>",
    "Content-Type":      "application/vnd.api+json"
  },

  beforeSend: function(data) {
    console.log("beforeSend");
  },

  success: function(data) {
    console.log("success");
    console.log(data);
  },

  error: function(data) {
    console.log("error");
  },

  complete: function(data) {
    console.log("complete!");
  }
});
```

```bash
curl -iX GET \
  https://valiant.finance/api/v1/options/entity_type \
  -H "X-AUTH-ID:         <API_ID>" \
  -H "X-AUTH-SIGNED-KEY: <API_SIGNED_KEY>" \
  -H "Content-Type:      application/vnd.api+json"
```

> Example successful response

If a request is successful, a JSON response will include a collection of valid options, with an option in the format <code>{ "label": "Example Label", "value": "example_value" }</code> where the label component can be used for display purposes, and the value component as the accepted value.

```json
{
    "label": "Example Label", "value": "example_value"
}
```

## Equipment Class

| Item              | Details                                                         |
| ----------------- | -------------------------------------------------------         |
| Endpoint          | `/api/v1/options/equipment_class`                               |
| Supported methods | `GET`                                                           |
| Description       | Returns a collection of equipment class label and value pairs.  |


### Corresponding Attributes

| Resource          | Attribute                                                  |
| ----------------- | -------------------------------------------------------    |
| [Lead](#leads)    | `equipment_class`                                          |



### Response

> Example request

```javascript
xhr = new XMLHttpRequest();

xhr.open("GET", "https://valiant.finance/api/v1/options/equipment_class");
xhr.setRequestHeader("X-AUTH-ID",         "<API_ID>")
xhr.setRequestHeader("X-AUTH-SIGNED-KEY", "<API_SIGNED_KEY>");
xhr.setRequestHeader("Content-Type",      "application/vnd.api+json");

xhr.onreadystatechange = function () {
  if (xhr.readyState == 4) {
    console.log(xhr.status);
    console.log(xhr.responseText);
  }
}

xhr.send();
```

```jquery

$.ajax({
  url: "https://valiant.finance/api/v1/options/equipment_class",
  type: "GET",
  contentType: "application/vnd.api+json",
  headers: {
    "X-AUTH-ID":         "<API_ID>",
    "X-AUTH-SIGNED-KEY": "<API_SIGNED_KEY>",
    "Content-Type":      "application/vnd.api+json"
  },

  beforeSend: function(data) {
    console.log("beforeSend");
  },

  success: function(data) {
    console.log("success");
    console.log(data);
  },

  error: function(data) {
    console.log("error");
  },

  complete: function(data) {
    console.log("complete!");
  }
});
```

```bash
curl -iX GET \
  https://valiant.finance/api/v1/options/equipment_class \
  -H "X-AUTH-ID:         <API_ID>" \
  -H "X-AUTH-SIGNED-KEY: <API_SIGNED_KEY>" \
  -H "Content-Type:      application/vnd.api+json"
```

> Example successful response

If a request is successful, a JSON response will include a collection of valid options, with an option in the format <code>{ "label": "Example Label", "value": "example_value" }</code> where the label component can be used for display purposes, and the value component as the accepted value.

```json
{
    "label": "Example Label", "value": "example_value"
}
```

## Industry

| Item              | Details                                                         |
| ----------------- | -------------------------------------------------------         |
| Endpoint          | `/api/v1/options/industry`                                      |
| Supported methods | `GET`                                                           |
| Description       | Returns a collection of industry label and value pairs.         |


### Corresponding Attributes

| Resource          | Attribute                                                  |
| ----------------- | -------------------------------------------------------    |
| [Lead](#leads)    | `industry`                                                 |



### Response

> Example request

```javascript
xhr = new XMLHttpRequest();

xhr.open("GET", "https://valiant.finance/api/v1/options/industry");
xhr.setRequestHeader("X-AUTH-ID",         "<API_ID>")
xhr.setRequestHeader("X-AUTH-SIGNED-KEY", "<API_SIGNED_KEY>");
xhr.setRequestHeader("Content-Type",      "application/vnd.api+json");

xhr.onreadystatechange = function () {
  if (xhr.readyState == 4) {
    console.log(xhr.status);
    console.log(xhr.responseText);
  }
}

xhr.send();
```

```jquery

$.ajax({
  url: "https://valiant.finance/api/v1/options/industry",
  type: "GET",
  contentType: "application/vnd.api+json",
  headers: {
    "X-AUTH-ID":         "<API_ID>",
    "X-AUTH-SIGNED-KEY": "<API_SIGNED_KEY>",
    "Content-Type":      "application/vnd.api+json"
  },

  beforeSend: function(data) {
    console.log("beforeSend");
  },

  success: function(data) {
    console.log("success");
    console.log(data);
  },

  error: function(data) {
    console.log("error");
  },

  complete: function(data) {
    console.log("complete!");
  }
});
```

```bash
curl -iX GET \
  https://valiant.finance/api/v1/options/industry \
  -H "X-AUTH-ID:         <API_ID>" \
  -H "X-AUTH-SIGNED-KEY: <API_SIGNED_KEY>" \
  -H "Content-Type:      application/vnd.api+json"
```

> Example successful response

If a request is successful, a JSON response will include a collection of valid options, with an option in the format <code>{ "label": "Example Label", "value": "example_value" }</code> where the label component can be used for display purposes, and the value component as the accepted value.

```json
{
    "label": "Example Label", "value": "example_value"
}
```


## Loan Purpose

| Item              | Details                                                    |
| ----------------- | -------------------------------------------------------    |
| Endpoint          | `/api/v1/options/loan_purpose`                             |
| Supported methods | `GET`                                                      |
| Description       | Returns a collection of loan purpose label and value pairs.|


### Corresponding Attributes

| Resource          | Attribute                                                  |
| ----------------- | -------------------------------------------------------    |
| [Lead](#leads)    | `loan_purpose`                                             |


### Response

> Example request

```javascript
xhr = new XMLHttpRequest();

xhr.open("GET", "https://valiant.finance/api/v1/options/loan_purpose");
xhr.setRequestHeader("X-AUTH-ID",         "<API_ID>")
xhr.setRequestHeader("X-AUTH-SIGNED-KEY", "<API_SIGNED_KEY>");
xhr.setRequestHeader("Content-Type",      "application/vnd.api+json");

xhr.onreadystatechange = function () {
  if (xhr.readyState == 4) {
    console.log(xhr.status);
    console.log(xhr.responseText);
  }
}

xhr.send();
```

```jquery

$.ajax({
  url: "https://valiant.finance/api/v1/options/loan_purpose",
  type: "GET",
  contentType: "application/vnd.api+json",
  headers: {
    "X-AUTH-ID":         "<API_ID>",
    "X-AUTH-SIGNED-KEY": "<API_SIGNED_KEY>",
    "Content-Type":      "application/vnd.api+json"
  },

  beforeSend: function(data) {
    console.log("beforeSend");
  },

  success: function(data) {
    console.log("success");
    console.log(data);
  },

  error: function(data) {
    console.log("error");
  },

  complete: function(data) {
    console.log("complete!");
  }
});
```

```bash
curl -iX GET \
  https://valiant.finance/api/v1/options/loan_purpose \
  -H "X-AUTH-ID:         <API_ID>" \
  -H "X-AUTH-SIGNED-KEY: <API_SIGNED_KEY>" \
  -H "Content-Type:      application/vnd.api+json"
```

> Example successful response

If a request is successful, a JSON response will include a collection of valid options, with an option in the format <code>{ "label": "Example Label", "value": "example_value" }</code> where the label component can be used for display purposes, and the value component as the accepted value.

```json
{
    "label": "Example Label", "value": "example_value"
}
```
