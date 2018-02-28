# Leads

🏅

Our Lead API allows third parties to directly submit Leads to Valiant via the API.

## Create a Lead

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

> Example response

```json
{
  "data": {
    "id": "6bbba93f-48c4-413b-88cf-de6436ccb20c",
    "type": "leads",
    "attributes": {
      "created-at": "2018-02-01T00:00:00.001Z"
    }
  }
}
```

| Item              | Details                                             |
| ----------------- | --------------------------------------------------- |
| Endpoint          | `/api/v1/leads`                                     |
| Supported methods | `POST`                                              |
| Description       | Submits a Lead with the given details to Valiant.   |

### Accepted Params

| Attribute        | Required? | Type      | Description                            |
| ---------------- | --------- | --------- | -------------------------------------- |
| first_name       | `true`    | `string`  | A string less than 255 characters long |
| last_name        | `true`    | `string`  | A string less than 255 characters long |
| phone            | `true`    | `string`  | Must be an Australian phone number and can begin with all valid local area codes, 1800 or 1300. |
| email            | `true`    | `string`  | Must conform to a valid email address. |
| requested_amount | `false`   | `integer` | The amount of the loan being requested. Must be a value greater than 0 if provided.	|
| months_trading   | `false`   | `integer` | The months the Lead's business has been trading. Must be a value greater than 0 if provided. |
