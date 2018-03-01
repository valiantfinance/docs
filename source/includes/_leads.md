# Leads

🏅

Our Lead API allows third parties to directly submit Leads to Valiant via the API.

## Create a Lead

| Item              | Details                                             |
| ----------------- | --------------------------------------------------- |
| Endpoint          | `/api/v1/leads`                                     |
| Supported methods | `POST`                                              |
| Description       | Submits a Lead with the given details to Valiant.   |

### Parameters

> Example request

```javascript
var params = {
  "first_name":     "Isaac",
  "last_name":      "Newton",
  "phone":          "0400000000",
  "email":          "api@valiant.finance",
  "months_trading": "12"
}

xhr = new XMLHttpRequest();

xhr.open("POST", "https://mercury-summer.valiant.finance/api/v1/leads");
xhr.setRequestHeader("X-AUTH-ID",         "<API_ID>")
xhr.setRequestHeader("X-AUTH-SIGNED-KEY", "<API_SIGNED_KEY>");
xhr.setRequestHeader("Content-Type",      "application/vnd.api+json");

xhr.onreadystatechange = function () {
  if (xhr.readyState == 4) {
    console.log(xhr.status);
    console.log(xhr.responseText);
  }
}

xhr.send(JSON.stringify(params));
```

```shell
curl -iX POST \
  https://mercury-summer.valiant.finance/api/v1/leads \
  -H "X-AUTH-ID:         <API_ID>" \
  -H "X-AUTH-SIGNED-KEY: <API_SIGNED_KEY>" \
  -H "Content-Type:      application/vnd.api+json" \
  -d '{
        "first_name":     "Isaac",
        "last_name":      "Newton",
        "email":          "api@valiant.finance",
        "phone":          "0400000000",
        "months_trading": "12"
      }'
```

Below lists a detail of accepted parameters that can be posted to the endpoint as a part of a valid `JSON` payload. A number of attributes are required.

| Attribute              | Type      | Required | Description                           |
| ---------------------- | --------- | :------: | ------------------------------------- |
| **`first_name`**       | `string`  | ✓        | Must be less than 255 characters long |
| **`last_name`**        | `string`  | ✓        | Must be less than 255 characters long |
| **`phone`**            | `string`  | ✓        | Must be an Australian phone number and can begin with all valid local area codes, 1800 or 1300. |
| **`email`**            | `string`  | ✓        | Must conform to a valid email address. |
| **`requested_amount`** | `integer` |          | The amount of the loan being requested. Must be a value greater than 0 if provided. |
| **`months_trading`**   | `integer` |          | The months the Lead's business has been trading. Must be a value greater than 0 if provided. |

### Response

> Example successful response

```json
{
  "data": {
    "id": "6bbba93f-48c4-413b-88cf-de6436ccb20c",
    "type": "leads",
    "attributes": {
      "created_at": "2017-08-17T00:00:00.001Z"
    }
  }
}
```

If a request is successful, a [`json:api`](http://jsonapi.org/) compliant `JSON` response will be delivered with all resource related information in a `data` key.

| Data             | Description                                                                 |
| ---------------- | --------------------------------------------------------------------------- |
| **`id`**         | A unique identifier in `uuid` format generated for the resource by Valiant. |
| **`type`**       | Pluralized name of the resource called on.                                  |
| **`attributes`** | A map with values of resource attributes.                                   |

### Attributes

The values of attributes included in the `attributes` hash are:

| Attribute        | Description                                 |
| ---------------- | ------------------------------------------- |
| **`created_at`** | The UTC datetime the resource was created.  |

<aside class="notice">
  Future releases of the Valiant API will allow the lookup of Leads using the returned <code>id</code> here as a reference. Be sure to store the returned <code>id</code> if you think you might want to look up the Lead at a later date.
</aside>
